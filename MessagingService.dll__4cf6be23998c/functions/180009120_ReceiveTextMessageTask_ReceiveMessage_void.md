# ReceiveTextMessageTask::_ReceiveMessage(void)

- ea: `0x180009120`
- end: `0x1800093dc`
- name: `?_ReceiveMessage@ReceiveTextMessageTask@@AEAAJXZ`
- size: `700`
- prototype: `__int64 __fastcall(ReceiveTextMessageTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180007d50`

## callees

- `0x1800044dc`
- `0x1800068f8`
- `0x180008168`
- `0x1800088dc`
- `0x180009120`
- `0x18000aa50`
- `0x18000c010`

## string_xrefs

- `0x180009140`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`

## pseudocode

```c
__int64 __fastcall ReceiveTextMessageTask::_ReceiveMessage(ReceiveTextMessageTask *this)
{
  struct ISmMessageSMS *v1; // rbx
  int ReplacementMessage; // eax
  unsigned int v4; // esi
  __int64 v5; // rax
  struct ISmMessageSMS *v6; // rdi
  int v7; // eax
  int v8; // eax
  unsigned int v9; // edi
  struct ISmMessageSMS *v11; // rdi
  int v12; // esi
  int v13; // eax
  int v14; // eax
  struct ISmMessageSMS *v15; // [rsp+30h] [rbp-48h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 5) + 132LL) )
  {
    v15 = 0;
    ReplacementMessage = ReceiveTextMessageTask::_FindReplacementMessage(this, &v15);
    v4 = ReplacementMessage;
    if ( ReplacementMessage < 0 )
    {
      Log_HREvent_0(
        (unsigned int)ReplacementMessage,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
      if ( v15 )
      {
        v5 = *(_QWORD *)v15;
LABEL_12:
        (*(void (**)(void))(v5 + 16))();
        goto LABEL_13;
      }
      goto LABEL_13;
    }
    v6 = v15;
    if ( !v15 )
      goto LABEL_17;
    LODWORD(v15) = 1;
    v7 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *, struct ISmMessageSMS **))(*(_QWORD *)v6 + 24LL))(v6, &v15);
    v4 = v7;
    if ( v7 < 0
      || (_DWORD)v15
      && ((v7 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *, _QWORD))(*(_QWORD *)v6 + 32LL))(v6, 0),
           v4 = v7,
           v7 < 0)
       || (v7 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v6 + 232LL))(v6), v4 = v7, v7 < 0)) )
    {
      Log_HREvent_0(
        (unsigned int)v7,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
      if ( v6 )
      {
        v5 = *(_QWORD *)v6;
        goto LABEL_12;
      }
LABEL_13:
      Log_HREvent_0(
        v4,
        0,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
      goto LABEL_17;
    }
    if ( v6 )
      (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v6 + 8LL))(v6);
    v1 = v6;
    (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v6 + 16LL))(v6);
  }
LABEL_17:
  v15 = 0;
  v8 = ReceiveTextMessageTask::_CreateStoreMessage(this, &v15);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = v15;
    v12 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v15 + 232LL))(v15);
    if ( v12 < 0 )
      goto LABEL_24;
    v13 = LogReceiveSmsEvent(v11);
    if ( v13 < 0 )
      Log_HREvent_0(
        (unsigned int)v13,
        0,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v1 )
    {
      v14 = (*(__int64 (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v1 + 208LL))(v1);
      if ( v14 < 0 )
        Log_HREvent_0(
          (unsigned int)v14,
          0,
          "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 112LL))(*((_QWORD *)this + 3));
    if ( v12 < 0 )
    {
LABEL_24:
      Log_HREvent_0(
        (unsigned int)v12,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
      if ( v11 )
        (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v1 )
        (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v1 + 16LL))(v1);
      return (unsigned int)v12;
    }
    else
    {
      if ( v11 )
        (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v1 )
        (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v1 + 16LL))(v1);
      return 0;
    }
  }
  else
  {
    Log_HREvent_0(
      (unsigned int)v8,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v15 )
      (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v1 )
      (*(void (__fastcall **)(struct ISmMessageSMS *))(*(_QWORD *)v1 + 16LL))(v1);
    return v9;
  }
}

```

## disassembly

```asm
0x180009120  push    rbx
0x180009122  push    rbp
0x180009123  push    rsi
0x180009124  push    rdi
0x180009125  push    r12
0x180009127  push    r15
0x180009129  sub     rsp, 48h
0x18000912d  mov     rax, cs:__security_cookie
0x180009134  xor     rax, rsp
0x180009137  mov     [rsp+78h+var_40], rax
0x18000913c  mov     rax, [rcx+28h]
0x180009140  lea     r15, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180009147  xor     ebx, ebx
0x180009149  mov     rbp, rcx
0x18000914c  lea     r12d, [rbx+1]
0x180009150  cmp     [rax+84h], ebx
0x180009156  jz      loc_18000926D
0x18000915c  lea     rdx, [rsp+78h+var_48]; struct ISmMessage **
0x180009161  mov     [rsp+78h+var_48], rbx
0x180009166  call    ?_FindReplacementMessage@ReceiveTextMessageTask@@AEAAJPEAPEAUISmMessage@@@Z; ReceiveTextMessageTask::_FindReplacementMessage(ISmMessage * *)
0x18000916b  mov     esi, eax
0x18000916d  test    eax, eax
0x18000916f  jns     short loc_18000919A
0x180009171  mov     r9d, 0E5h
0x180009177  mov     r8, r15
0x18000917a  mov     edx, r12d
0x18000917d  mov     ecx, eax
0x18000917f  call    Log_HREvent_0
0x180009184  mov     rcx, [rsp+78h+var_48]
0x180009189  test    rcx, rcx
0x18000918c  jz      loc_180009233
0x180009192  mov     rax, [rcx]
0x180009195  jmp     loc_18000922A
0x18000919a  mov     rdi, [rsp+78h+var_48]
0x18000919f  test    rdi, rdi
0x1800091a2  jz      loc_18000926D
0x1800091a8  mov     dword ptr [rsp+78h+var_48], r12d
0x1800091ad  lea     rdx, [rsp+78h+var_48]
0x1800091b2  mov     rax, [rdi]
0x1800091b5  mov     rcx, rdi
0x1800091b8  mov     rax, [rax+18h]
0x1800091bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091c1  mov     esi, eax
0x1800091c3  test    eax, eax
0x1800091c5  jns     short loc_1800091CF
0x1800091c7  mov     r9d, 0EFh
0x1800091cd  jmp     short loc_180009212
0x1800091cf  cmp     dword ptr [rsp+78h+var_48], ebx
0x1800091d3  jz      short loc_180009247
0x1800091d5  mov     rax, [rdi]
0x1800091d8  xor     edx, edx
0x1800091da  mov     rcx, rdi
0x1800091dd  mov     rax, [rax+20h]
0x1800091e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091e6  mov     esi, eax
0x1800091e8  test    eax, eax
0x1800091ea  jns     short loc_1800091F4
0x1800091ec  mov     r9d, 0F2h
0x1800091f2  jmp     short loc_180009212
0x1800091f4  mov     rax, [rdi]
0x1800091f7  mov     rcx, rdi
0x1800091fa  mov     rax, [rax+0E8h]
0x180009201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009206  mov     esi, eax
0x180009208  test    eax, eax
0x18000920a  jns     short loc_180009247
0x18000920c  mov     r9d, 0F3h
0x180009212  mov     r8, r15
0x180009215  mov     edx, r12d
0x180009218  mov     ecx, eax
0x18000921a  call    Log_HREvent_0
0x18000921f  test    rdi, rdi
0x180009222  jz      short loc_180009233
0x180009224  mov     rax, [rdi]
0x180009227  mov     rcx, rdi
0x18000922a  mov     rax, [rax+10h]
0x18000922e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009233  mov     r9d, 86h
0x180009239  mov     r8, r15
0x18000923c  xor     edx, edx
0x18000923e  mov     ecx, esi
0x180009240  call    Log_HREvent_0
0x180009245  jmp     short loc_18000926D
0x180009247  test    rdi, rdi
0x18000924a  jz      short loc_18000925B
0x18000924c  mov     rax, [rdi]
0x18000924f  mov     rcx, rdi
0x180009252  mov     rax, [rax+8]
0x180009256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000925b  mov     rax, [rdi]
0x18000925e  mov     rcx, rdi
0x180009261  mov     rbx, rdi
0x180009264  mov     rax, [rax+10h]
0x180009268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000926d  lea     rdx, [rsp+78h+var_48]; struct ISmMessageSMS **
0x180009272  mov     [rsp+78h+var_48], 0
0x18000927b  mov     rcx, rbp; this
0x18000927e  call    ?_CreateStoreMessage@ReceiveTextMessageTask@@AEAAJPEAPEAUISmMessageSMS@@@Z; ReceiveTextMessageTask::_CreateStoreMessage(ISmMessageSMS * *)
0x180009283  mov     edi, eax
0x180009285  test    eax, eax
0x180009287  jns     short loc_1800092CD
0x180009289  mov     r9d, 8Ah
0x18000928f  mov     r8, r15
0x180009292  mov     edx, r12d
0x180009295  mov     ecx, eax
0x180009297  call    Log_HREvent_0
0x18000929c  mov     rcx, [rsp+78h+var_48]
0x1800092a1  test    rcx, rcx
0x1800092a4  jz      short loc_1800092B2
0x1800092a6  mov     rdx, [rcx]
0x1800092a9  mov     rax, [rdx+10h]
0x1800092ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b2  test    rbx, rbx
0x1800092b5  jz      short loc_1800092C6
0x1800092b7  mov     rax, [rbx]
0x1800092ba  mov     rcx, rbx
0x1800092bd  mov     rax, [rax+10h]
0x1800092c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092c6  mov     eax, edi
0x1800092c8  jmp     loc_1800093C2
0x1800092cd  mov     rdi, [rsp+78h+var_48]
0x1800092d2  mov     rcx, rdi
0x1800092d5  mov     rax, [rdi]
0x1800092d8  mov     rax, [rax+0E8h]
0x1800092df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092e4  mov     esi, eax
0x1800092e6  test    eax, eax
0x1800092e8  jns     short loc_18000932C
0x1800092ea  mov     r9d, 8Ch
0x1800092f0  mov     r8, r15
0x1800092f3  mov     edx, r12d
0x1800092f6  mov     ecx, esi
0x1800092f8  call    Log_HREvent_0
0x1800092fd  test    rdi, rdi
0x180009300  jz      short loc_180009311
0x180009302  mov     rcx, [rdi]
0x180009305  mov     rax, [rcx+10h]
0x180009309  mov     rcx, rdi
0x18000930c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009311  test    rbx, rbx
0x180009314  jz      short loc_180009325
0x180009316  mov     rax, [rbx]
0x180009319  mov     rcx, rbx
0x18000931c  mov     rax, [rax+10h]
0x180009320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009325  mov     eax, esi
0x180009327  jmp     loc_1800093C2
0x18000932c  mov     rcx, rdi; struct ISmMessageSMS *
0x18000932f  call    ?LogReceiveSmsEvent@@YAJPEAUISmMessageSMS@@@Z; LogReceiveSmsEvent(ISmMessageSMS *)
0x180009334  test    eax, eax
0x180009336  jns     short loc_18000934A
0x180009338  mov     r9d, 8Eh
0x18000933e  mov     r8, r15
0x180009341  xor     edx, edx
0x180009343  mov     ecx, eax
0x180009345  call    Log_HREvent_0
0x18000934a  test    rbx, rbx
0x18000934d  jz      short loc_180009377
0x18000934f  mov     rax, [rbx]
0x180009352  mov     rcx, rbx
0x180009355  mov     rax, [rax+0D0h]
0x18000935c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009361  test    eax, eax
0x180009363  jns     short loc_180009377
0x180009365  mov     r9d, 97h
0x18000936b  mov     r8, r15
0x18000936e  xor     edx, edx
0x180009370  mov     ecx, eax
0x180009372  call    Log_HREvent_0
0x180009377  mov     rcx, [rbp+18h]
0x18000937b  mov     rax, [rcx]
0x18000937e  mov     rax, [rax+70h]
0x180009382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009387  mov     esi, eax
0x180009389  test    eax, eax
0x18000938b  jns     short loc_180009398
0x18000938d  mov     r9d, 9Bh
0x180009393  jmp     loc_1800092F0
0x180009398  test    rdi, rdi
0x18000939b  jz      short loc_1800093AC
0x18000939d  mov     rax, [rdi]
0x1800093a0  mov     rcx, rdi
0x1800093a3  mov     rax, [rax+10h]
0x1800093a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ac  test    rbx, rbx
0x1800093af  jz      short loc_1800093C0
0x1800093b1  mov     rax, [rbx]
0x1800093b4  mov     rcx, rbx
0x1800093b7  mov     rax, [rax+10h]
0x1800093bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c0  xor     eax, eax
0x1800093c2  mov     rcx, [rsp+78h+var_40]
0x1800093c7  xor     rcx, rsp; StackCookie
0x1800093ca  call    __security_check_cookie
0x1800093cf  add     rsp, 48h
0x1800093d3  pop     r15
0x1800093d5  pop     r12
0x1800093d7  pop     rdi
0x1800093d8  pop     rsi
0x1800093d9  pop     rbp
0x1800093da  pop     rbx
0x1800093db  retn
```

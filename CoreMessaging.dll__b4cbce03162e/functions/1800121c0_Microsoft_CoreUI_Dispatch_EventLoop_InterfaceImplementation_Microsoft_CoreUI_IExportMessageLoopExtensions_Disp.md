# Microsoft::CoreUI::Dispatch::EventLoop::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageLoopExtensions::Dispatcher::Wait(System::Object *,uint,Microsoft::CoreUI::Support::Win32Handle *,uint,Microsoft::CoreUI::WaitFlags)

- ea: `0x1800121c0`
- end: `0x180012570`
- name: `?Wait@Dispatcher@_Microsoft_CoreUI_IExportMessageLoopExtensions@InterfaceImplementation$@EventLoop@Dispatch@CoreUI@Microsoft@@UEBA?AW4WaitStatus@567@PEAVObject@System@@IPEAUWin32Handle@Support@67@IW4WaitFlags@67@@Z`
- size: `944`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ec10`
- `0x180010ed0`
- `0x1800111dc`
- `0x180011cec`
- `0x1800121c0`
- `0x180012580`
- `0x180013b60`
- `0x18003950c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800124ae`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800124ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800121fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800121fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::CoreUI::Dispatch::EventLoop::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageLoopExtensions::Dispatcher::Wait(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        int a6)
{
  int v6; // r14d
  int v7; // r13d
  unsigned int v8; // r15d
  char v10; // r12
  __int64 v11; // rbx
  System::Object *v12; // rbx
  __int64 v13; // rbx
  bool v14; // cc
  __int64 v15; // rdi
  System::Object *v16; // r14
  char v17; // r15
  __int64 v18; // r14
  int v19; // eax
  char v20; // al
  char v21; // r13
  System::Object *v22; // rbx
  __int64 v23; // rcx
  System::Object *v24; // rdi
  int v25; // eax
  unsigned int v26; // esi
  unsigned int v27; // ebx
  signed int LastError; // eax
  __int64 v30; // [rsp+40h] [rbp-39h]
  System::Object *v31[2]; // [rsp+58h] [rbp-21h] BYREF
  __int128 v32; // [rsp+68h] [rbp-11h]
  __int128 v33; // [rsp+78h] [rbp-1h]
  __int64 v34; // [rsp+88h] [rbp+Fh]
  System::Object *v35; // [rsp+D8h] [rbp+5Fh] BYREF
  unsigned int v36; // [rsp+E0h] [rbp+67h]
  __int64 v37; // [rsp+E8h] [rbp+6Fh]

  v37 = a4;
  v36 = a3;
  v7 = a4;
  v8 = a3;
  v10 = 0;
  LODWORD(v35) = 0;
  v11 = *(_QWORD *)(a2 + 48);
  if ( GetCurrentThreadId() != *(_DWORD *)(v11 + 176) )
  {
    Microsoft::CoreUI::Messaging::MessagingValidationException::FromResult(&v35, 4);
    System::Exception::Throw$(v35);
    goto LABEL_60;
  }
  if ( !*(_BYTE *)(a2 + 32) && (*(_DWORD *)(a2 + 64) || *(_DWORD *)(a2 + 72)) )
  {
    Microsoft::CoreUI::Messaging::MessagingValidationException::FromResult(&v35, 2);
    System::Exception::Throw$(v35);
    goto LABEL_77;
  }
  *(_BYTE *)(a2 + 80) = 1;
  v33 = 0u;
  v31[0] = 0;
  v31[1] = 0;
  v32 = 0u;
  v34 = 0;
  v6 = a6;
  if ( (a6 & 2) == 0 )
  {
    v12 = *(System::Object **)(a2 + 168);
    v35 = v12;
    if ( v12 )
      ++*((_DWORD *)v12 + 4);
    LOBYTE(v7) = (*(__int64 (__fastcall **)(System::Object *))(*(_QWORD *)v12 + 104LL))(v12);
    if ( v12 )
      System::Object::ReleaseNotFrozen$(v12);
    if ( !*(_DWORD *)(a2 + 180) )
    {
      v13 = *(_QWORD *)(a2 + 56);
      if ( v13 )
        ++*(_DWORD *)(v13 + 16);
      v10 = 64;
      LODWORD(v35) = 64;
      v14 = *(_DWORD *)(v13 + 56) <= 0;
      if ( !*(_DWORD *)(v13 + 56) )
      {
        v15 = *(_QWORD *)(v13 + 32);
        if ( v15 )
          ++*(_DWORD *)(v15 + 16);
        if ( *(_DWORD *)(v15 + 64) != 2 && *(_DWORD *)(v15 + 68) != 5 && *(_DWORD *)(v15 + 76) != 4 )
        {
          v16 = *(System::Object **)(v15 + 168);
          if ( v16 )
            ++*((_DWORD *)v16 + 4);
          v17 = (*(__int64 (__fastcall **)(System::Object *))(*(_QWORD *)v16 + 120LL))(v16);
          if ( v16 )
            System::Object::ReleaseNotFrozen$(v16);
          if ( !v17 )
          {
            v18 = *(_QWORD *)(v15 + 96);
            if ( v18 )
            {
              v19 = *(_DWORD *)(v18 + 16);
              if ( v19 > 0 )
                *(_DWORD *)(v18 + 16) = v19 + 1;
            }
            if ( *(_DWORD *)(v18 + 24) == 1 )
              (*(void (__fastcall **)(_QWORD))(v18 + 40))(*(_QWORD *)(v18 + 48));
            else
              CFlat::DelegateImpl<System::Action,0,void (void),void,0>::MulticastInvoke(v18);
            if ( v18 )
              System::Object::Release$((System::Object *)v18);
          }
          v6 = a6;
          v8 = v36;
        }
        if ( v15 )
          System::Object::ReleaseNotFrozen$((System::Object *)v15);
        v14 = *(_DWORD *)(v13 + 56) <= 0;
      }
      if ( !v14 )
      {
        v20 = 1;
LABEL_37:
        v21 = v20 | v7;
        if ( (v10 & 0x40) != 0 && v13 )
          System::Object::ReleaseNotFrozen$((System::Object *)v13);
        if ( !v21 )
        {
          v7 = v37;
          goto LABEL_42;
        }
        if ( ResetEvent(*(HANDLE *)(a2 + 144)) )
        {
          v26 = a5;
          goto LABEL_53;
        }
LABEL_77:
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        CFlat::Abandonment::FailWithHR(LastError, 0, 0);
      }
LABEL_36:
      v20 = 0;
      goto LABEL_37;
    }
LABEL_60:
    v13 = v30;
    goto LABEL_36;
  }
LABEL_42:
  v22 = *(System::Object **)(a2 + 168);
  if ( v22 )
    ++*((_DWORD *)v22 + 4);
  v23 = *(_QWORD *)(*(__int64 (__fastcall **)(System::Object *, System::Object **))(*(_QWORD *)v22 + 200LL))(v22, &v35);
  v24 = *(System::Object **)(a2 + 160);
  if ( v24 )
  {
    v25 = *((_DWORD *)v24 + 4);
    if ( v25 > 0 )
      *((_DWORD *)v24 + 4) = v25 + 1;
  }
  v26 = a5;
  Microsoft::CoreUI::Dispatch::WaitCollection::Callback_DoGeneralWait(v23, v8, v7, a5, v6, (__int64)v31, (__int64)v24);
  if ( v24 )
    System::Object::Release$(v24);
  if ( v35 )
    System::Object::ReleaseNotFrozen$(v35);
  if ( v22 )
    System::Object::ReleaseNotFrozen$(v22);
LABEL_53:
  if ( !(_BYTE)v33 )
    goto LABEL_67;
  v27 = (unsigned int)v31[1];
  if ( LODWORD(v31[1]) == 43963 )
  {
    v27 = HIDWORD(v32);
    goto LABEL_56;
  }
  if ( LODWORD(v31[1]) <= 0xABBA )
  {
    if ( LODWORD(v31[1]) != 43962
      && LODWORD(v31[1])
      && LODWORD(v31[1]) != 128
      && (LODWORD(v31[1]) != 258 || DWORD2(v32) >= v26) )
    {
      goto LABEL_56;
    }
LABEL_67:
    v27 = v8;
    goto LABEL_56;
  }
  if ( LODWORD(v31[1]) == 43964 )
  {
    v27 = HIDWORD(v32) + 128;
  }
  else if ( LODWORD(v31[1]) == 43965 )
  {
    v27 = -1;
  }
LABEL_56:
  if ( v31[0] )
    System::Object::ReleaseNotFrozen$(v31[0]);
  return v27;
}

```

## disassembly

```asm
0x1800121c0  mov     [rsp-8+arg_0], rbx
0x1800121c5  mov     [rsp-8+arg_18], r9
0x1800121ca  mov     [rsp-8+arg_10], r8d
0x1800121cf  push    rbp
0x1800121d0  push    rsi
0x1800121d1  push    rdi
0x1800121d2  push    r12
0x1800121d4  push    r13
0x1800121d6  push    r14
0x1800121d8  push    r15
0x1800121da  lea     rbp, [rsp-17h]
0x1800121df  sub     rsp, 90h
0x1800121e6  mov     r13, r9
0x1800121e9  mov     r15d, r8d
0x1800121ec  mov     rsi, rdx
0x1800121ef  xor     edi, edi
0x1800121f1  mov     r12d, edi
0x1800121f4  mov     dword ptr [rbp+47h+arg_8], edi
0x1800121f7  mov     rbx, [rdx+30h]
0x1800121fb  call    cs:__imp_GetCurrentThreadId
0x180012201  cmp     eax, [rbx+0B0h]
0x180012207  jnz     loc_180012485
0x18001220d  cmp     [rsi+20h], dil
0x180012211  jnz     short loc_180012225
0x180012213  cmp     [rsi+40h], edi
0x180012216  jnz     loc_18001252A
0x18001221c  cmp     [rsi+48h], edi
0x18001221f  jnz     loc_18001252A
0x180012225  mov     byte ptr [rsi+50h], 1
0x180012229  xorps   xmm0, xmm0
0x18001222c  xor     eax, eax
0x18001222e  movups  xmmword ptr [rbp+47h+var_68], xmm0
0x180012232  movups  [rbp+47h+var_58], xmm0
0x180012236  movups  [rbp+47h+var_48], xmm0
0x18001223a  mov     [rbp+47h+var_68], rdi
0x18001223e  mov     dword ptr [rbp+47h+var_68+8], edi
0x180012241  mov     qword ptr [rbp+47h+var_58], rdi
0x180012245  mov     qword ptr [rbp+47h+var_58+8], rdi
0x180012249  mov     byte ptr [rbp+47h+var_48], al
0x18001224c  movdqu  [rbp+47h+var_48+8], xmm0
0x180012251  mov     [rbp+47h+var_38], rdi
0x180012255  mov     r14d, [rbp+47h+arg_28]
0x180012259  test    r14b, 2
0x18001225d  jnz     loc_1800123AA
0x180012263  mov     rbx, [rsi+0A8h]
0x18001226a  mov     [rbp+47h+arg_8], rbx
0x18001226e  test    rbx, rbx
0x180012271  jz      short loc_180012276
0x180012273  inc     dword ptr [rbx+10h]
0x180012276  mov     rax, [rbx]
0x180012279  mov     rcx, rbx
0x18001227c  mov     rax, [rax+68h]
0x180012280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012285  movzx   r13d, al
0x180012289  test    rbx, rbx
0x18001228c  jz      short loc_180012296
0x18001228e  mov     rcx, rbx; this
0x180012291  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012296  cmp     dword ptr [rsi+0B4h], 0
0x18001229d  ja      loc_18001249E
0x1800122a3  mov     rbx, [rsi+38h]
0x1800122a7  mov     [rbp+47h+var_80], rbx
0x1800122ab  test    rbx, rbx
0x1800122ae  jz      short loc_1800122B3
0x1800122b0  inc     dword ptr [rbx+10h]
0x1800122b3  mov     r12d, 40h ; '@'
0x1800122b9  mov     dword ptr [rbp+47h+arg_8], r12d
0x1800122bd  cmp     dword ptr [rbx+38h], 0
0x1800122c1  jnz     loc_18001237F
0x1800122c7  mov     rdi, [rbx+20h]
0x1800122cb  mov     [rbp+47h+var_78], rdi
0x1800122cf  test    rdi, rdi
0x1800122d2  jz      short loc_1800122D7
0x1800122d4  inc     dword ptr [rdi+10h]
0x1800122d7  cmp     dword ptr [rdi+40h], 2
0x1800122db  jz      loc_18001236E
0x1800122e1  cmp     dword ptr [rdi+44h], 5
0x1800122e5  jz      loc_18001236E
0x1800122eb  cmp     dword ptr [rdi+4Ch], 4
0x1800122ef  jz      short loc_18001236E
0x1800122f1  mov     r14, [rdi+0A8h]
0x1800122f8  mov     [rbp+47h+var_70], r14
0x1800122fc  test    r14, r14
0x1800122ff  jz      short loc_180012305
0x180012301  inc     dword ptr [r14+10h]
0x180012305  mov     rax, [r14]
0x180012308  mov     rcx, r14
0x18001230b  mov     rax, [rax+78h]
0x18001230f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012314  movzx   r15d, al
0x180012318  test    r14, r14
0x18001231b  jz      short loc_180012325
0x18001231d  mov     rcx, r14; this
0x180012320  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012325  test    r15b, r15b
0x180012328  jnz     short loc_180012366
0x18001232a  mov     r14, [rdi+60h]
0x18001232e  mov     [rbp+47h+var_70], r14
0x180012332  test    r14, r14
0x180012335  jz      short loc_180012345
0x180012337  mov     eax, [r14+10h]
0x18001233b  test    eax, eax
0x18001233d  jle     short loc_180012345
0x18001233f  inc     eax
0x180012341  mov     [r14+10h], eax
0x180012345  cmp     dword ptr [r14+18h], 1
0x18001234a  jz      loc_1800124DF
0x180012350  mov     rcx, r14
0x180012353  call    ?MulticastInvoke@?$DelegateImpl@VAction@System@@$0A@$$A6AXXZX$0A@@CFlat@@AEBAXXZ; CFlat::DelegateImpl<System::Action,0,void (void),void,0>::MulticastInvoke(void)
0x180012358  nop
0x180012359  test    r14, r14
0x18001235c  jz      short loc_180012366
0x18001235e  mov     rcx, r14; this
0x180012361  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180012366  mov     r14d, [rbp+47h+arg_28]
0x18001236a  mov     r15d, [rbp+47h+arg_10]
0x18001236e  test    rdi, rdi
0x180012371  jz      short loc_18001237B
0x180012373  mov     rcx, rdi; this
0x180012376  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18001237b  cmp     dword ptr [rbx+38h], 0
0x18001237f  jg      loc_1800124F1
0x180012385  xor     al, al
0x180012387  or      r13b, al
0x18001238a  test    r12b, 40h
0x18001238e  jz      short loc_18001239D
0x180012390  test    rbx, rbx
0x180012393  jz      short loc_18001239D
0x180012395  mov     rcx, rbx; this
0x180012398  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18001239d  test    r13b, r13b
0x1800123a0  jnz     loc_1800124A7
0x1800123a6  mov     r13, [rbp+47h+arg_18]
0x1800123aa  mov     rbx, [rsi+0A8h]
0x1800123b1  mov     [rbp+47h+var_70], rbx
0x1800123b5  test    rbx, rbx
0x1800123b8  jz      short loc_1800123BD
0x1800123ba  inc     dword ptr [rbx+10h]
0x1800123bd  mov     rax, [rbx]
0x1800123c0  lea     rdx, [rbp+47h+arg_8]
0x1800123c4  mov     rcx, rbx
0x1800123c7  mov     rax, [rax+0C8h]
0x1800123ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123d3  nop
0x1800123d4  mov     rcx, [rax]
0x1800123d7  mov     rdi, [rsi+0A0h]
0x1800123de  mov     [rbp+47h+var_78], rdi
0x1800123e2  test    rdi, rdi
0x1800123e5  jz      short loc_1800123F3
0x1800123e7  mov     eax, [rdi+10h]
0x1800123ea  test    eax, eax
0x1800123ec  jle     short loc_1800123F3
0x1800123ee  inc     eax
0x1800123f0  mov     [rdi+10h], eax
0x1800123f3  mov     [rsp+0C0h+var_90], rdi
0x1800123f8  lea     rax, [rbp+47h+var_68]
0x1800123fc  mov     [rsp+0C0h+var_98], rax
0x180012401  mov     [rsp+0C0h+var_A0], r14d
0x180012406  mov     esi, [rbp+47h+arg_20]
0x180012409  mov     r9d, esi
0x18001240c  mov     r8, r13
0x18001240f  mov     edx, r15d
0x180012412  call    ?Callback_DoGeneralWait@WaitCollection@Dispatch@CoreUI@Microsoft@@QEAAXIPEAUWin32Handle@Support@34@IW4WaitFlags@34@U?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVWakeRecordHandler@234@@Z; Microsoft::CoreUI::Dispatch::WaitCollection::Callback_DoGeneralWait(uint,Microsoft::CoreUI::Support::Win32Handle *,uint,Microsoft::CoreUI::WaitFlags,CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>,Microsoft::CoreUI::Dispatch::WakeRecordHandler *)
0x180012417  nop
0x180012418  test    rdi, rdi
0x18001241b  jz      short loc_180012426
0x18001241d  mov     rcx, rdi; this
0x180012420  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180012425  nop
0x180012426  mov     rcx, [rbp+47h+arg_8]; this
0x18001242a  test    rcx, rcx
0x18001242d  jz      short loc_180012435
0x18001242f  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012434  nop
0x180012435  test    rbx, rbx
0x180012438  jz      short loc_180012442
0x18001243a  mov     rcx, rbx; this
0x18001243d  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012442  cmp     byte ptr [rbp+47h+var_48], 0
0x180012446  jz      loc_1800124D7
0x18001244c  mov     ebx, dword ptr [rbp+47h+var_68+8]
0x18001244f  cmp     ebx, 0ABBBh
0x180012455  jnz     short loc_1800124C1
0x180012457  mov     ebx, dword ptr [rbp+47h+var_58+0Ch]
0x18001245a  mov     rcx, [rbp+47h+var_68]; this
0x18001245e  test    rcx, rcx
0x180012461  jz      short loc_180012468
0x180012463  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012468  mov     eax, ebx
0x18001246a  mov     rbx, [rsp+0C0h+arg_0]
0x180012472  add     rsp, 90h
0x180012479  pop     r15
0x18001247b  pop     r14
0x18001247d  pop     r13
0x18001247f  pop     r12
0x180012481  pop     rdi
0x180012482  pop     rsi
0x180012483  pop     rbp
0x180012484  retn
0x180012485  mov     edx, 4
0x18001248a  lea     rcx, [rbp+47h+arg_8]
0x18001248e  call    ?FromResult@MessagingValidationException@Messaging@CoreUI@Microsoft@@SA?AV?$SmartPtr@VException@System@@@CFlat@@W4MessagingResults@234@@Z; Microsoft::CoreUI::Messaging::MessagingValidationException::FromResult(Microsoft::CoreUI::Messaging::MessagingResults)
0x180012493  nop
0x180012494  mov     rcx, [rbp+47h+arg_8]; this
0x180012498  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x18001249d  nop
0x18001249e  mov     rbx, [rbp+47h+var_80]
0x1800124a2  jmp     loc_180012385
0x1800124a7  mov     rcx, [rsi+90h]; hEvent
0x1800124ae  call    cs:__imp_ResetEvent
0x1800124b4  test    eax, eax
0x1800124b6  jz      loc_180012543
0x1800124bc  mov     esi, [rbp+47h+arg_20]
0x1800124bf  jmp     short loc_180012442
0x1800124c1  cmp     ebx, 0ABBAh
0x1800124c7  ja      short loc_1800124F8
0x1800124c9  jz      short loc_1800124D7
0x1800124cb  test    ebx, ebx
0x1800124cd  jz      short loc_1800124D7
0x1800124cf  cmp     ebx, 80h
0x1800124d5  jnz     short loc_180012514
0x1800124d7  mov     ebx, r15d
0x1800124da  jmp     loc_18001245A
0x1800124df  mov     rcx, [r14+30h]
0x1800124e3  mov     rax, [r14+28h]
0x1800124e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124ec  jmp     loc_180012359
0x1800124f1  mov     al, 1
0x1800124f3  jmp     loc_180012387
0x1800124f8  mov     eax, ebx
0x1800124fa  sub     eax, 0ABBCh
0x1800124ff  jz      short loc_180012564
0x180012501  cmp     eax, 1
0x180012504  jnz     loc_18001245A
0x18001250a  mov     ebx, 0FFFFFFFFh
0x18001250f  jmp     loc_18001245A
0x180012514  cmp     ebx, 102h
0x18001251a  jnz     loc_18001245A
0x180012520  cmp     dword ptr [rbp+47h+var_58+8], esi
0x180012523  jb      short loc_1800124D7
0x180012525  jmp     loc_18001245A
0x18001252a  mov     edx, 2
0x18001252f  lea     rcx, [rbp+47h+arg_8]
0x180012533  call    ?FromResult@MessagingValidationException@Messaging@CoreUI@Microsoft@@SA?AV?$SmartPtr@VException@System@@@CFlat@@W4MessagingResults@234@@Z; Microsoft::CoreUI::Messaging::MessagingValidationException::FromResult(Microsoft::CoreUI::Messaging::MessagingResults)
0x180012538  nop
0x180012539  mov     rcx, [rbp+47h+arg_8]; this
0x18001253d  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x180012542  nop
0x180012543  call    cs:__imp_GetLastError
0x180012549  test    eax, eax
0x18001254b  jg      short loc_18001255A
0x18001254d  xor     r8d, r8d; int
0x180012550  xor     edx, edx; void *
0x180012552  mov     ecx, eax; int
0x180012554  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18001255a  movzx   eax, ax
0x18001255d  or      eax, 80070000h
0x180012562  jmp     short loc_18001254D
0x180012564  mov     ebx, dword ptr [rbp+47h+var_58+0Ch]
0x180012567  sub     ebx, 0FFFFFF80h
0x18001256a  jmp     loc_18001245A
```

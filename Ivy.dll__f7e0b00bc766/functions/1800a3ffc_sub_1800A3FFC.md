# sub_1800A3FFC

- ea: `0x1800a3ffc`
- end: `0x1800a4202`
- name: `sub_1800A3FFC`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a3720`

## callees

- `0x180011ac4`
- `0x180011ae8`
- `0x1800647dc`
- `0x180065528`
- `0x1800a3ffc`
- `0x18016ba7c`
- `0x18016d174`
- `0x18016eaf0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x1800a406c`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800a4162`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800a406c`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800a4162`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a4095`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a4095`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall sub_1800A3FFC(__int64 a1, int *a2, void (__fastcall ****a3)(_QWORD), bool *a4)
{
  __int64 v8; // rax
  bool result; // al
  _QWORD *v10; // rdi
  void (__fastcall ***v11)(_QWORD); // rcx
  int v12; // eax
  _DWORD *i; // rcx
  __int64 v14; // rdx
  void (__fastcall ***v15)(_QWORD, __int64); // rbx
  _QWORD *v16; // r14
  _QWORD *v17; // r15
  __int64 v18; // rbx
  __int64 v19; // rax
  bool v20; // al
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  int v22; // [rsp+20h] [rbp-28h] BYREF
  struct Ivy::IRefCounted **v23; // [rsp+28h] [rbp-20h]
  _QWORD *v24; // [rsp+58h] [rbp+10h] BYREF

  if ( a4 )
    *a4 = 0;
  v22 = *a2;
  v23 = &Ivy::IRefCounted * `RTTI Type Descriptor';
  v8 = sub_1800647DC(&qword_18021D800, &enum ChartPlayer::ResultType `RTTI Type Descriptor', &v22);
  if ( (_UNKNOWN *)v8 == &enum ChartPlayer::ResultType `RTTI Type Descriptor' || *(_DWORD *)v8 != *a2 )
  {
    if ( (unsigned int)*a2 < 0x2710 )
    {
      sub_180011AE8(508646801, &qword_1801AB2B8);
      sub_180011AC4(508646801, "Missing entry in PropertyTypeMap");
    }
    result = 1;
  }
  else
  {
    result = (unsigned int)_std_type_info_compare(*(_QWORD *)(v8 + 8) + 8LL, &qword_18021FE28) == 0;
  }
  if ( result )
  {
    v10 = malloc(0x10u);
    if ( !v10 )
      Concurrency::cancel_current_task();
    v11 = *a3;
    *v10 = &Ivy::PropertyStorage<enum Ivy::PropertyId>::PropertyValue<Ivy::IRefCounted *,void>::`vftable';
    v10[1] = v11;
    if ( v11 )
      (**v11)(v11);
    v24 = v10;
    v12 = *a2;
    for ( i = *(_DWORD **)a1; i != *(_DWORD **)(a1 + 8) && v12 != *i; i += 4 )
      ;
    v14 = *(_QWORD *)(a1 + 8);
    if ( i == (_DWORD *)v14 )
    {
      if ( a4 )
        *a4 = 1;
      if ( v14 == *(_QWORD *)(a1 + 16) )
      {
        sub_180065528(a1, v14, a2, &v24);
      }
      else
      {
        *(_DWORD *)v14 = v12;
        v24 = 0;
        *(_QWORD *)(v14 + 8) = v10;
        *(_QWORD *)(a1 + 8) += 16LL;
      }
      v15 = (void (__fastcall ***)(_QWORD, __int64))v24;
    }
    else
    {
      v16 = i + 2;
      if ( a4 )
      {
        v17 = (_QWORD *)*v16;
        v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
        v19 = (*(__int64 (__fastcall **)(_QWORD *))(*v10 + 8LL))(v10);
        v20 = 1;
        if ( !(unsigned int)_std_type_info_compare(v18 + 8, v19 + 8) )
        {
          sub_18016D174(*v17, 20600, 0);
          if ( v17[1] == v10[1] )
            v20 = 0;
        }
        *a4 = v20;
      }
      v15 = 0;
      v21 = (void (__fastcall ***)(_QWORD, __int64))*v16;
      *v16 = v10;
      if ( v21 )
        (**v21)(v21, 1);
    }
    if ( v15 )
      (**v15)(v15, 1);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800a3ffc  mov     [rsp+arg_0], rbx
0x1800a4001  mov     [rsp+arg_10], rsi
0x1800a4006  push    rdi
0x1800a4007  push    r14
0x1800a4009  push    r15
0x1800a400b  sub     rsp, 30h
0x1800a400f  mov     rsi, r9
0x1800a4012  mov     r15, r8
0x1800a4015  mov     r14, rdx
0x1800a4018  mov     rbx, rcx
0x1800a401b  test    r9, r9
0x1800a401e  jz      short loc_1800A4024
0x1800a4020  mov     byte ptr [r9], 0
0x1800a4024  mov     eax, [rdx]
0x1800a4026  mov     [rsp+48h+var_28], eax
0x1800a402a  lea     rax, ??_R0PEAUIRefCounted@Ivy@@@8; Ivy::IRefCounted * `RTTI Type Descriptor'
0x1800a4031  mov     [rsp+48h+var_20], rax
0x1800a4036  lea     r8, [rsp+48h+var_28]
0x1800a403b  lea     rdi, ??_R0?AW4ResultType@ChartPlayer@@@8; ChartPlayer::ResultType `RTTI Type Descriptor'
0x1800a4042  mov     rdx, rdi
0x1800a4045  lea     rcx, qword_18021D800
0x1800a404c  call    sub_1800647DC
0x1800a4051  cmp     rax, rdi
0x1800a4054  jz      short loc_1800A4079
0x1800a4056  mov     ecx, [r14]
0x1800a4059  cmp     [rax], ecx
0x1800a405b  jnz     short loc_1800A4079
0x1800a405d  mov     rcx, [rax+8]
0x1800a4061  add     rcx, 8
0x1800a4065  lea     rdx, qword_18021FE28
0x1800a406c  call    cs:__std_type_info_compare
0x1800a4072  test    eax, eax
0x1800a4074  setz    al
0x1800a4077  jmp     short loc_1800A4088
0x1800a4079  cmp     dword ptr [r14], 2710h
0x1800a4080  jb      loc_1800A41E0
0x1800a4086  mov     al, 1
0x1800a4088  test    al, al
0x1800a408a  jz      loc_1800A41C6
0x1800a4090  mov     ecx, 10h; Size
0x1800a4095  call    cs:malloc
0x1800a409b  mov     rdi, rax
0x1800a409e  test    rax, rax
0x1800a40a1  jz      loc_1800A41DA
0x1800a40a7  mov     rcx, [r15]
0x1800a40aa  lea     rax, ??_7?$PropertyValue@PEAUIRefCounted@Ivy@@X@?$PropertyStorage@W4PropertyId@Ivy@@@Ivy@@6B@; const Ivy::PropertyStorage<Ivy::PropertyId>::PropertyValue<Ivy::IRefCounted *,void>::`vftable'
0x1800a40b1  mov     [rdi], rax
0x1800a40b4  mov     [rdi+8], rcx
0x1800a40b8  test    rcx, rcx
0x1800a40bb  jz      short loc_1800A40C9
0x1800a40bd  mov     rax, [rcx]
0x1800a40c0  mov     rax, [rax]
0x1800a40c3  call    cs:__guard_dispatch_icall_fptr
0x1800a40c9  mov     [rsp+48h+arg_8], rdi
0x1800a40ce  mov     eax, [r14]
0x1800a40d1  mov     rcx, [rbx]
0x1800a40d4  jmp     short loc_1800A40DE
0x1800a40d6  cmp     eax, [rcx]
0x1800a40d8  jz      short loc_1800A40E4
0x1800a40da  add     rcx, 10h
0x1800a40de  cmp     rcx, [rbx+8]
0x1800a40e2  jnz     short loc_1800A40D6
0x1800a40e4  mov     rdx, [rbx+8]
0x1800a40e8  cmp     rcx, rdx
0x1800a40eb  jnz     short loc_1800A412B
0x1800a40ed  test    rsi, rsi
0x1800a40f0  jz      short loc_1800A40F5
0x1800a40f2  mov     byte ptr [rsi], 1
0x1800a40f5  cmp     rdx, [rbx+10h]
0x1800a40f9  jz      short loc_1800A4111
0x1800a40fb  mov     [rdx], eax
0x1800a40fd  mov     [rsp+48h+arg_8], 0
0x1800a4106  mov     [rdx+8], rdi
0x1800a410a  add     qword ptr [rbx+8], 10h
0x1800a410f  jmp     short loc_1800A4121
0x1800a4111  lea     r9, [rsp+48h+arg_8]
0x1800a4116  mov     r8, r14
0x1800a4119  mov     rcx, rbx
0x1800a411c  call    sub_180065528
0x1800a4121  mov     rbx, [rsp+48h+arg_8]
0x1800a4126  jmp     loc_1800A41AB
0x1800a412b  lea     r14, [rcx+8]
0x1800a412f  test    rsi, rsi
0x1800a4132  jz      short loc_1800A418E
0x1800a4134  mov     r15, [r14]
0x1800a4137  mov     rax, [r15]
0x1800a413a  mov     rcx, r15
0x1800a413d  mov     rax, [rax+8]
0x1800a4141  call    cs:__guard_dispatch_icall_fptr
0x1800a4147  mov     rbx, rax
0x1800a414a  mov     rcx, [rdi]
0x1800a414d  mov     rax, [rcx+8]
0x1800a4151  mov     rcx, rdi
0x1800a4154  call    cs:__guard_dispatch_icall_fptr
0x1800a415a  lea     rdx, [rax+8]
0x1800a415e  lea     rcx, [rbx+8]
0x1800a4162  call    cs:__std_type_info_compare
0x1800a4168  test    eax, eax
0x1800a416a  jnz     short loc_1800A418A
0x1800a416c  xor     r8d, r8d
0x1800a416f  mov     edx, 5078h
0x1800a4174  mov     rcx, [r15]
0x1800a4177  call    sub_18016D174
0x1800a417c  mov     rax, [rdi+8]
0x1800a4180  cmp     [r15+8], rax
0x1800a4184  jnz     short loc_1800A418A
0x1800a4186  xor     al, al
0x1800a4188  jmp     short loc_1800A418C
0x1800a418a  mov     al, 1
0x1800a418c  mov     [rsi], al
0x1800a418e  xor     ebx, ebx
0x1800a4190  mov     rcx, [r14]
0x1800a4193  mov     [r14], rdi
0x1800a4196  test    rcx, rcx
0x1800a4199  jz      short loc_1800A41AB
0x1800a419b  mov     rax, [rcx]
0x1800a419e  lea     edx, [rbx+1]
0x1800a41a1  mov     rax, [rax]
0x1800a41a4  call    cs:__guard_dispatch_icall_fptr
0x1800a41aa  nop
0x1800a41ab  test    rbx, rbx
0x1800a41ae  jz      short loc_1800A41C4
0x1800a41b0  mov     rcx, [rbx]
0x1800a41b3  mov     rax, [rcx]
0x1800a41b6  mov     edx, 1
0x1800a41bb  mov     rcx, rbx
0x1800a41be  call    cs:__guard_dispatch_icall_fptr
0x1800a41c4  mov     al, 1
0x1800a41c6  mov     rbx, [rsp+48h+arg_0]
0x1800a41cb  mov     rsi, [rsp+48h+arg_10]
0x1800a41d0  add     rsp, 30h
0x1800a41d4  pop     r15
0x1800a41d6  pop     r14
0x1800a41d8  pop     rdi
0x1800a41d9  retn
0x1800a41da  call    ?cancel_current_task@Concurrency@@YAXXZ_1; Concurrency::cancel_current_task(void)
0x1800a41e0  lea     rdx, qword_1801AB2B8
0x1800a41e7  mov     ebx, 1E515591h
0x1800a41ec  mov     ecx, ebx
0x1800a41ee  call    sub_180011AE8
0x1800a41f3  lea     rdx, aMissingEntryIn; "Missing entry in PropertyTypeMap"
0x1800a41fa  mov     ecx, ebx
0x1800a41fc  call    sub_180011AC4
```

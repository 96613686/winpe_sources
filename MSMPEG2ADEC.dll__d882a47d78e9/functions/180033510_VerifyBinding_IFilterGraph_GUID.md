# VerifyBinding(IFilterGraph *,_GUID)

- ea: `0x180033510`
- end: `0x1800336d5`
- name: `?VerifyBinding@@YAJPEAUIFilterGraph@@U_GUID@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(struct IFilterGraph *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011860`

## callees

- `0x180002056`
- `0x1800331e4`
- `0x180033510`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800336a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800336a8`

## pseudocode

```c
__int64 __fastcall VerifyBinding(struct IFilterGraph *a1, struct _GUID *a2)
{
  int v4; // edi
  int v5; // ebx
  __time64_t v6; // rax
  struct _GUID v7; // xmm0
  __int64 v8; // rax
  __int64 v10; // [rsp+40h] [rbp-30h] BYREF
  __int64 v11; // [rsp+48h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-20h] BYREF
  struct _GUID v13; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+90h] [rbp+20h] BYREF
  __int64 *v15; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF

  v11 = 0;
  v15 = 0;
  v16 = 0;
  pv[0] = 0;
  v14 = 0;
  v10 = 0;
  if ( !a1 )
    return 2147500035LL;
  v4 = 0;
  v5 = ((__int64 (__fastcall *)(struct IFilterGraph *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &IID_IServiceProvider,
         &v11);
  if ( v5 )
    goto LABEL_13;
  if ( v11 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v11 + 24LL))(
           v11,
           &IID_IValidateBinding,
           &IID_IUnknown,
           &v16);
    if ( v5 )
      goto LABEL_13;
    if ( v16 )
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v16)(
             v16,
             &GUID_04a578b2_e778_422a_a805_b3ee54d90bd9,
             &v15);
      if ( v5 )
      {
LABEL_13:
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        goto LABEL_15;
      }
      if ( v15 )
      {
        v6 = time64_0(0);
        v7 = *a2;
        v10 = v6;
        v8 = *v15;
        v13 = v7;
        v5 = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *, __int64 *, _QWORD, LPVOID *, unsigned int *))(v8 + 24))(
               v15,
               &v13,
               &v10,
               (unsigned int)(v5 + 8),
               pv,
               &v14);
        if ( v5 >= 0 )
        {
          v13 = *a2;
          v4 = CheckValidationBlob(&v13, (unsigned __int8 *)pv[0], v14, v10);
        }
        goto LABEL_13;
      }
    }
    v5 = -2147418113;
    goto LABEL_13;
  }
  v5 = -2147418113;
LABEL_15:
  if ( v15 )
    (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( v5 < 0 || v4 < 0 )
    return (unsigned int)(v4 | v5);
  else
    return (unsigned int)v4;
}

```

## disassembly

```asm
0x180033510  mov     [rsp-18h+arg_8], rbx
0x180033515  push    rbp
0x180033516  push    rsi
0x180033517  push    rdi
0x180033518  mov     rbp, rsp
0x18003351b  sub     rsp, 70h
0x18003351f  mov     [rbp+var_28], 0
0x180033527  mov     rsi, rdx
0x18003352a  mov     [rbp+arg_10], 0
0x180033532  mov     [rbp+arg_18], 0
0x18003353a  mov     [rbp+pv], 0
0x180033542  mov     [rbp+arg_0], 0
0x180033549  mov     [rbp+var_30], 0
0x180033551  test    rcx, rcx
0x180033554  jnz     short loc_180033560
0x180033556  mov     eax, 80004003h
0x18003355b  jmp     loc_1800336C4
0x180033560  mov     rax, [rcx]
0x180033563  lea     r8, [rbp+var_28]
0x180033567  lea     rdx, IID_IServiceProvider
0x18003356e  xor     edi, edi
0x180033570  mov     rax, [rax]
0x180033573  call    cs:__guard_dispatch_icall_fptr
0x180033579  mov     ebx, eax
0x18003357b  test    eax, eax
0x18003357d  jnz     loc_18003365D
0x180033583  mov     rcx, [rbp+var_28]
0x180033587  test    rcx, rcx
0x18003358a  jnz     short loc_180033596
0x18003358c  mov     ebx, 8000FFFFh
0x180033591  jmp     loc_180033673
0x180033596  mov     rax, [rcx]
0x180033599  lea     r9, [rbp+arg_18]
0x18003359d  lea     r8, IID_IUnknown
0x1800335a4  lea     rdx, IID_IValidateBinding
0x1800335ab  mov     rax, [rax+18h]
0x1800335af  call    cs:__guard_dispatch_icall_fptr
0x1800335b5  mov     ebx, eax
0x1800335b7  test    eax, eax
0x1800335b9  jnz     loc_18003365D
0x1800335bf  cmp     [rbp+arg_18], rdi
0x1800335c3  jnz     short loc_1800335CF
0x1800335c5  mov     ebx, 8000FFFFh
0x1800335ca  jmp     loc_18003365D
0x1800335cf  mov     rcx, [rbp+arg_18]
0x1800335d3  lea     r8, [rbp+arg_10]
0x1800335d7  lea     rdx, _GUID_04a578b2_e778_422a_a805_b3ee54d90bd9
0x1800335de  mov     rax, [rcx]
0x1800335e1  mov     rax, [rax]
0x1800335e4  call    cs:__guard_dispatch_icall_fptr
0x1800335ea  mov     ebx, eax
0x1800335ec  test    eax, eax
0x1800335ee  jnz     short loc_18003365D
0x1800335f0  cmp     [rbp+arg_10], rdi
0x1800335f4  jz      short loc_1800335C5
0x1800335f6  xor     ecx, ecx; Time
0x1800335f8  call    _time64_0
0x1800335fd  mov     rcx, [rbp+arg_10]
0x180033601  lea     rdx, [rbp+arg_0]
0x180033605  movaps  xmm0, xmmword ptr [rsi]
0x180033608  lea     r9d, [rbx+8]
0x18003360c  mov     [rsp+70h+var_48], rdx
0x180033611  lea     r8, [rbp+var_30]
0x180033615  mov     [rbp+var_30], rax
0x180033619  lea     rdx, [rbp+pv]
0x18003361d  mov     rax, [rcx]
0x180033620  mov     [rsp+70h+var_50], rdx
0x180033625  lea     rdx, [rbp+var_10]
0x180033629  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x18003362e  mov     rax, [rax+18h]
0x180033632  call    cs:__guard_dispatch_icall_fptr
0x180033638  mov     ebx, eax
0x18003363a  test    eax, eax
0x18003363c  js      short loc_18003365D
0x18003363e  movaps  xmm0, xmmword ptr [rsi]
0x180033641  lea     rcx, [rbp+var_10]; struct _GUID
0x180033645  mov     r9, [rbp+var_30]; __int64
0x180033649  mov     r8d, [rbp+arg_0]; unsigned int
0x18003364d  mov     rdx, [rbp+pv]; unsigned __int8 *
0x180033651  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x180033656  call    ?CheckValidationBlob@@YAJU_GUID@@PEAEK_J@Z; CheckValidationBlob(_GUID,uchar *,ulong,__int64)
0x18003365b  mov     edi, eax
0x18003365d  mov     rcx, [rbp+var_28]
0x180033661  test    rcx, rcx
0x180033664  jz      short loc_180033673
0x180033666  mov     rdx, [rcx]
0x180033669  mov     rax, [rdx+10h]
0x18003366d  call    cs:__guard_dispatch_icall_fptr
0x180033673  mov     rcx, [rbp+arg_10]
0x180033677  test    rcx, rcx
0x18003367a  jz      short loc_180033689
0x18003367c  mov     rax, [rcx]
0x18003367f  mov     rax, [rax+10h]
0x180033683  call    cs:__guard_dispatch_icall_fptr
0x180033689  mov     rcx, [rbp+arg_18]
0x18003368d  test    rcx, rcx
0x180033690  jz      short loc_18003369F
0x180033692  mov     rax, [rcx]
0x180033695  mov     rax, [rax+10h]
0x180033699  call    cs:__guard_dispatch_icall_fptr
0x18003369f  mov     rcx, [rbp+pv]; pv
0x1800336a3  test    rcx, rcx
0x1800336a6  jz      short loc_1800336B4
0x1800336a8  call    cs:__imp_CoTaskMemFree
0x1800336af  nop     dword ptr [rax+rax+00h]
0x1800336b4  test    ebx, ebx
0x1800336b6  js      short loc_1800336C0
0x1800336b8  test    edi, edi
0x1800336ba  js      short loc_1800336C0
0x1800336bc  mov     ebx, edi
0x1800336be  jmp     short loc_1800336C2
0x1800336c0  or      ebx, edi
0x1800336c2  mov     eax, ebx
0x1800336c4  mov     rbx, [rsp+70h+arg_8]
0x1800336cc  add     rsp, 70h
0x1800336d0  pop     rdi
0x1800336d1  pop     rsi
0x1800336d2  pop     rbp
0x1800336d3  retn
```

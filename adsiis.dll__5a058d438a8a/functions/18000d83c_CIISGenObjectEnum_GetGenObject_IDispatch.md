# CIISGenObjectEnum::GetGenObject(IDispatch * *)

- ea: `0x18000d83c`
- end: `0x18000dad7`
- name: `?GetGenObject@CIISGenObjectEnum@@AEAAJPEAPEAUIDispatch@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(CIISGenObjectEnum *__hidden this, struct IDispatch **)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18000dae0`

## callees

- `0x18000549c`
- `0x18000d83c`
- `0x180012ffc`
- `0x18001364c`
- `0x18001441c`
- `0x18001bc54`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000da17`
- `msvcrt!memcpy_s` at `0x18000da17`
- `msvcrt!wcsstr` at `0x18000d9b1`
- `msvcrt!wcsstr` at `0x18000d9d3`
- `msvcrt!wcsstr` at `0x18000d9b1`
- `msvcrt!wcsstr` at `0x18000d9d3`
- `msvcrt!_wcsupr` at `0x18000d99e`
- `msvcrt!_wcsupr` at `0x18000d99e`

## string_xrefs

- `0x18000d9c0`: `IIsWebDirectory`

## pseudocode

```c
__int64 __fastcall CIISGenObjectEnum::GetGenObject(CIISGenObjectEnum *this, struct IDispatch **a2)
{
  struct IMSAdminBaseW **v3; // r12
  unsigned int v4; // esi
  int inited; // ebx
  int v6; // eax
  struct IMSAdminBaseW *v7; // rcx
  int v8; // eax
  wchar_t *v9; // rbx
  rsize_t v10; // r9
  const wchar_t *v11; // r8
  const unsigned __int16 *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+44h] [rbp-BCh] BYREF
  void *v16; // [rsp+48h] [rbp-B8h] BYREF
  struct IDispatch **v17; // [rsp+50h] [rbp-B0h]
  __int128 v18; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v19; // [rsp+68h] [rbp-98h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  unsigned __int16 Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v22[264]; // [rsp+290h] [rbp+190h] BYREF

  v17 = a2;
  v20 = 0;
  v15 = 0;
  v3 = (struct IMSAdminBaseW **)((char *)this + 48);
  v14 = 0;
  *a2 = 0;
  v4 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  if ( !*((_QWORD *)this + 6) )
  {
    inited = InitServerInfo(
               (CIISGenObjectEnum *)((char *)this + 64),
               *((const unsigned __int16 **)this + 4),
               (struct IMSAdminBaseW **)this + 6,
               (struct IIsSchema **)this + 7);
    if ( inited < 0 )
      goto LABEL_16;
  }
  v6 = OpenAdminBaseKey(
         (CIISGenObjectEnum *)((char *)this + 64),
         *((unsigned __int16 **)this + 4),
         *((unsigned __int16 **)this + 5),
         1u,
         (struct IMSAdminBaseW **)this + 6,
         &v14);
  v4 = v14;
  inited = v6;
  if ( v6 < 0 )
    goto LABEL_16;
  inited = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, const OLECHAR *, unsigned __int16 *, _DWORD))(*v3)->lpVtbl->EnumKeys)(
             *v3,
             v14,
             &psz,
             v22,
             *((_DWORD *)this + 4));
  if ( inited < 0 )
    goto LABEL_16;
  v7 = *v3;
  LODWORD(v18) = 1002;
  *((_QWORD *)&v19 + 1) = Destination;
  HIDWORD(v18) = 2;
  *(_QWORD *)((char *)&v18 + 4) = 1;
  LODWORD(v19) = 260;
  v8 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, unsigned __int16 *, __int128 *, int *))v7->lpVtbl->GetData)(
         v7,
         v4,
         v22,
         &v18,
         &v15);
  inited = v8;
  if ( v8 >= 0 )
  {
    if ( (unsigned int)IIsSchema::ValidateClassName(*((IIsSchema **)this + 7), Destination) != -2147463153 )
      goto LABEL_14;
    goto LABEL_12;
  }
  if ( v8 != -2146646015 )
    goto LABEL_16;
  v9 = _wcsupr(*((wchar_t **)this + 5));
  if ( !wcsstr(v9, L"W3SVC") )
  {
    if ( wcsstr(v9, L"MSFTPSVC") )
    {
      v10 = 34;
      v11 = L"IIsFtpVirtualDir";
      goto LABEL_13;
    }
LABEL_12:
    v10 = 20;
    v11 = L"IIsObject";
    goto LABEL_13;
  }
  v10 = 32;
  v11 = L"IIsWebDirectory";
LABEL_13:
  memcpy_s(Destination, 0x208u, v11, v10);
LABEL_14:
  v12 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  ++*((_DWORD *)this + 4);
  inited = CIISGenObject::CreateGenericObject(
             v12,
             v22,
             Destination,
             (CIISGenObjectEnum *)((char *)this + 64),
             1u,
             &IID_IDispatch,
             &v16);
  if ( inited >= 0 )
    inited = (**(__int64 (__fastcall ***)(void *, GUID *, struct IDispatch **))v16)(v16, &IID_IDispatch, v17);
LABEL_16:
  if ( *v3 && v4 )
    CloseAdminBaseKey(*v3, v4);
  if ( v16 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
  if ( inited < 0 )
    return 1;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000d83c  mov     [rsp-8+arg_10], rbx
0x18000d841  push    rbp
0x18000d842  push    rsi
0x18000d843  push    rdi
0x18000d844  push    r12
0x18000d846  push    r13
0x18000d848  push    r14
0x18000d84a  push    r15
0x18000d84c  lea     rbp, [rsp-3B0h]
0x18000d854  sub     rsp, 4B0h
0x18000d85b  mov     rax, cs:__security_cookie
0x18000d862  xor     rax, rsp
0x18000d865  mov     [rbp+3E0h+var_40], rax
0x18000d86c  mov     rdi, rcx
0x18000d86f  mov     [rsp+4E0h+var_490], rdx
0x18000d874  mov     rax, rdx
0x18000d877  xor     ecx, ecx
0x18000d879  xor     edx, edx
0x18000d87b  mov     [rsp+4E0h+var_468], rcx
0x18000d880  xorps   xmm0, xmm0
0x18000d883  mov     [rsp+4E0h+var_49C], edx
0x18000d887  lea     r12, [rdi+30h]
0x18000d88b  mov     [rsp+4E0h+var_4A0], edx
0x18000d88f  mov     [rax], rdx
0x18000d892  lea     r13, [rdi+40h]
0x18000d896  mov     esi, edx
0x18000d898  mov     [rsp+4E0h+var_498], rdx
0x18000d89d  movups  [rsp+4E0h+var_488], xmm0
0x18000d8a2  movups  [rsp+4E0h+var_478], xmm0
0x18000d8a7  cmp     [r12], rdx
0x18000d8ab  jnz     short loc_18000D8CA
0x18000d8ad  mov     rdx, [rdi+20h]; unsigned __int16 *
0x18000d8b1  lea     r9, [rdi+38h]; struct IIsSchema **
0x18000d8b5  mov     r8, r12; struct IMSAdminBaseW **
0x18000d8b8  mov     rcx, r13; struct CCredentials *
0x18000d8bb  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x18000d8c0  mov     ebx, eax
0x18000d8c2  test    eax, eax
0x18000d8c4  js      loc_18000DA75
0x18000d8ca  mov     r8, [rdi+28h]; unsigned __int16 *
0x18000d8ce  lea     rax, [rsp+4E0h+var_4A0]
0x18000d8d3  mov     rdx, [rdi+20h]; unsigned __int16 *
0x18000d8d7  mov     r9d, 1; unsigned int
0x18000d8dd  mov     [rsp+4E0h+var_4B8], rax; unsigned int *
0x18000d8e2  mov     rcx, r13; this
0x18000d8e5  mov     [rsp+4E0h+var_4C0], r12; struct IMSAdminBaseW **
0x18000d8ea  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x18000d8ef  mov     esi, [rsp+4E0h+var_4A0]
0x18000d8f3  mov     ebx, eax
0x18000d8f5  test    eax, eax
0x18000d8f7  js      loc_18000DA75
0x18000d8fd  mov     r10, [r12]
0x18000d901  lea     r9, [rbp+3E0h+var_250]
0x18000d908  mov     ecx, [rdi+10h]
0x18000d90b  lea     r8, psz
0x18000d912  mov     dword ptr [rsp+4E0h+var_4C0], ecx
0x18000d916  mov     edx, esi
0x18000d918  mov     rcx, r10
0x18000d91b  mov     rax, [r10]
0x18000d91e  mov     rax, [rax+30h]
0x18000d922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d927  mov     ebx, eax
0x18000d929  mov     r14d, 1
0x18000d92f  test    eax, eax
0x18000d931  js      loc_18000DA7B
0x18000d937  mov     rcx, [r12]
0x18000d93b  lea     rdx, [rsp+4E0h+var_49C]
0x18000d940  lea     rax, [rbp+3E0h+Destination]
0x18000d944  mov     dword ptr [rsp+4E0h+var_488], 3EAh
0x18000d94c  mov     qword ptr [rsp+4E0h+var_478+8], rax
0x18000d951  lea     r9, [rsp+4E0h+var_488]
0x18000d956  mov     dword ptr [rsp+4E0h+var_488+0Ch], 2
0x18000d95e  lea     r8, [rbp+3E0h+var_250]
0x18000d965  mov     qword ptr [rsp+4E0h+var_488+4], 1
0x18000d96e  mov     dword ptr [rsp+4E0h+var_478], 104h
0x18000d976  mov     rax, [rcx]
0x18000d979  mov     [rsp+4E0h+var_4C0], rdx
0x18000d97e  mov     edx, esi
0x18000d980  mov     rax, [rax+50h]
0x18000d984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d989  mov     ebx, eax
0x18000d98b  test    eax, eax
0x18000d98d  jns     short loc_18000D9ED
0x18000d98f  cmp     eax, 800CC801h
0x18000d994  jnz     loc_18000DA7B
0x18000d99a  mov     rcx, [rdi+28h]; String
0x18000d99e  call    cs:__imp__wcsupr
0x18000d9a4  mov     rcx, rax; Str
0x18000d9a7  lea     rdx, aW3svc; "W3SVC"
0x18000d9ae  mov     rbx, rax
0x18000d9b1  call    cs:__imp_wcsstr
0x18000d9b7  test    rax, rax
0x18000d9ba  jz      short loc_18000D9C9
0x18000d9bc  lea     r9d, [r14+1Fh]
0x18000d9c0  lea     r8, aIiswebdirector_1; "IIsWebDirectory"
0x18000d9c7  jmp     short loc_18000DA0E
0x18000d9c9  lea     rdx, aMsftpsvc; "MSFTPSVC"
0x18000d9d0  mov     rcx, rbx; Str
0x18000d9d3  call    cs:__imp_wcsstr
0x18000d9d9  test    rax, rax
0x18000d9dc  jz      short loc_18000DA01
0x18000d9de  mov     r9d, 22h ; '"'
0x18000d9e4  lea     r8, aIisftpvirtuald; "IIsFtpVirtualDir"
0x18000d9eb  jmp     short loc_18000DA0E
0x18000d9ed  mov     rcx, [rdi+38h]; this
0x18000d9f1  lea     rdx, [rbp+3E0h+Destination]; unsigned __int16 *
0x18000d9f5  call    ?ValidateClassName@IIsSchema@@QEAAJPEBG@Z; IIsSchema::ValidateClassName(ushort const *)
0x18000d9fa  cmp     eax, 8000500Fh
0x18000d9ff  jnz     short loc_18000DA1D
0x18000da01  mov     r9d, 14h; SourceSize
0x18000da07  lea     r8, aIisobject; "IIsObject"
0x18000da0e  mov     edx, 208h; DestinationSize
0x18000da13  lea     rcx, [rbp+3E0h+Destination]; Destination
0x18000da17  call    cs:__imp_memcpy_s
0x18000da1d  mov     rcx, [rdi+18h]; unsigned __int16 *
0x18000da21  lea     rax, [rsp+4E0h+var_498]
0x18000da26  add     [rdi+10h], r14d
0x18000da2a  lea     r15, IID_IDispatch
0x18000da31  mov     [rsp+4E0h+var_4B0], rax; void **
0x18000da36  lea     r8, [rbp+3E0h+Destination]; unsigned __int16 *
0x18000da3a  mov     [rsp+4E0h+var_4B8], r15; struct _GUID *
0x18000da3f  lea     rdx, [rbp+3E0h+var_250]; unsigned __int16 *
0x18000da46  mov     r9, r13; struct CCredentials *
0x18000da49  mov     dword ptr [rsp+4E0h+var_4C0], r14d; unsigned int
0x18000da4e  call    ?CreateGenericObject@CIISGenObject@@SAJPEBG00AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z; CIISGenObject::CreateGenericObject(ushort const *,ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)
0x18000da53  mov     ebx, eax
0x18000da55  test    eax, eax
0x18000da57  js      short loc_18000DA7B
0x18000da59  mov     rcx, [rsp+4E0h+var_498]
0x18000da5e  mov     rdx, r15
0x18000da61  mov     r8, [rsp+4E0h+var_490]
0x18000da66  mov     rax, [rcx]
0x18000da69  mov     rax, [rax]
0x18000da6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da71  mov     ebx, eax
0x18000da73  jmp     short loc_18000DA7B
0x18000da75  mov     r14d, 1
0x18000da7b  mov     rcx, [r12]; struct IMSAdminBaseW *
0x18000da7f  test    rcx, rcx
0x18000da82  jz      short loc_18000DA8F
0x18000da84  test    esi, esi
0x18000da86  jz      short loc_18000DA8F
0x18000da88  mov     edx, esi; unsigned int
0x18000da8a  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x18000da8f  mov     rcx, [rsp+4E0h+var_498]
0x18000da94  test    rcx, rcx
0x18000da97  jz      short loc_18000DAA5
0x18000da99  mov     rdx, [rcx]
0x18000da9c  mov     rax, [rdx+10h]
0x18000daa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa5  test    ebx, ebx
0x18000daa7  cmovs   ebx, r14d
0x18000daab  mov     eax, ebx
0x18000daad  mov     rcx, [rbp+3E0h+var_40]
0x18000dab4  xor     rcx, rsp; StackCookie
0x18000dab7  call    __security_check_cookie
0x18000dabc  mov     rbx, [rsp+4E0h+arg_10]
0x18000dac4  add     rsp, 4B0h
0x18000dacb  pop     r15
0x18000dacd  pop     r14
0x18000dacf  pop     r13
0x18000dad1  pop     r12
0x18000dad3  pop     rdi
0x18000dad4  pop     rsi
0x18000dad5  pop     rbp
0x18000dad6  retn
```

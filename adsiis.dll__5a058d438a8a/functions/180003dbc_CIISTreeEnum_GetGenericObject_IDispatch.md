# CIISTreeEnum::GetGenericObject(IDispatch * *)

- ea: `0x180003dbc`
- end: `0x180003fed`
- name: `?GetGenericObject@CIISTreeEnum@@AEAAJPEAPEAUIDispatch@@@Z`
- size: `561`
- prototype: `int(CIISTreeEnum *__hidden this, struct IDispatch **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180004000`

## callees

- `0x180003dbc`
- `0x18000549c`
- `0x180012ffc`
- `0x18001441c`
- `0x18001bc54`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003f64`
- `msvcrt!memcpy_s` at `0x180003f64`
- `msvcrt!wcsstr` at `0x180003ef9`
- `msvcrt!wcsstr` at `0x180003f1e`
- `msvcrt!wcsstr` at `0x180003ef9`
- `msvcrt!wcsstr` at `0x180003f1e`
- `msvcrt!_wcsupr` at `0x180003ee8`
- `msvcrt!_wcsupr` at `0x180003ee8`

## string_xrefs

- `0x180003f0a`: `IIsWebDirectory`

## pseudocode

```c
__int64 __fastcall CIISTreeEnum::GetGenericObject(CIISTreeEnum *this, struct IDispatch **a2)
{
  struct IMSAdminBaseW **v2; // r14
  unsigned __int16 *v3; // r8
  unsigned __int16 *v5; // rdx
  int GenericObject; // ebx
  struct IMSAdminBaseW *v8; // rcx
  int v9; // eax
  rsize_t v10; // r9
  const wchar_t *v11; // r8
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h]
  __int64 v17; // [rsp+68h] [rbp-98h]
  unsigned __int16 Destination[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v19[264]; // [rsp+280h] [rbp+180h] BYREF

  v14 = 0;
  *a2 = 0;
  v2 = (struct IMSAdminBaseW **)((char *)this + 56);
  v3 = (unsigned __int16 *)*((_QWORD *)this + 10);
  v17 = 0;
  v5 = (unsigned __int16 *)*((_QWORD *)this + 9);
  v13 = 0;
  v15 = 0;
  v16 = 0;
  GenericObject = OpenAdminBaseKey(
                    (CIISTreeEnum *)((char *)this + 32),
                    v5,
                    v3,
                    1u,
                    (struct IMSAdminBaseW **)this + 7,
                    &v13);
  if ( GenericObject >= 0 )
  {
    GenericObject = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, const OLECHAR *, unsigned __int16 *, _DWORD))(*v2)->lpVtbl->EnumKeys)(
                      *v2,
                      v13,
                      &psz,
                      v19,
                      *((_DWORD *)this + 4));
    if ( GenericObject >= 0 )
    {
      v8 = *v2;
      LODWORD(v15) = 1002;
      *((_QWORD *)&v16 + 1) = Destination;
      HIDWORD(v15) = 2;
      *(_QWORD *)((char *)&v15 + 4) = 1;
      LODWORD(v16) = 260;
      v9 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, unsigned __int16 *, __int128 *, int *))v8->lpVtbl->GetData)(
             v8,
             v13,
             v19,
             &v15,
             &v14);
      GenericObject = v9;
      if ( v9 >= 0 )
      {
        if ( (unsigned int)IIsSchema::ValidateClassName(*((IIsSchema **)this + 8), Destination) != -2147463153 )
        {
LABEL_12:
          ++*((_DWORD *)this + 4);
          GenericObject = CIISGenObject::CreateGenericObject(
                            *((const unsigned __int16 **)this + 3),
                            v19,
                            Destination,
                            (CIISTreeEnum *)((char *)this + 32),
                            1u,
                            &IID_IDispatch,
                            (void **)a2);
          goto LABEL_13;
        }
        goto LABEL_10;
      }
      if ( v9 == -2146646015 )
      {
        _wcsupr(*((wchar_t **)this + 10));
        if ( wcsstr(*((const wchar_t **)this + 10), L"W3SVC") )
        {
          v10 = 32;
          v11 = L"IIsWebDirectory";
LABEL_11:
          memcpy_s(Destination, 0x208u, v11, v10);
          goto LABEL_12;
        }
        if ( wcsstr(*((const wchar_t **)this + 10), L"MSFTPSVC") )
        {
          v10 = 34;
          v11 = L"IIsFtpVirtualDir";
          goto LABEL_11;
        }
LABEL_10:
        v10 = 20;
        v11 = L"IIsObject";
        goto LABEL_11;
      }
    }
  }
LABEL_13:
  if ( *v2 && v13 )
    CloseAdminBaseKey(*v2, v13);
  if ( GenericObject < 0 )
    return 1;
  return (unsigned int)GenericObject;
}

```

## disassembly

```asm
0x180003dbc  mov     [rsp-8+arg_10], rbx
0x180003dc1  push    rbp
0x180003dc2  push    rdi
0x180003dc3  push    r12
0x180003dc5  push    r14
0x180003dc7  push    r15
0x180003dc9  lea     rbp, [rsp-3A0h]
0x180003dd1  sub     rsp, 4A0h
0x180003dd8  mov     rax, cs:__security_cookie
0x180003ddf  xor     rax, rsp
0x180003de2  mov     [rbp+3C0h+var_30], rax
0x180003de9  xor     eax, eax
0x180003deb  mov     [rsp+4C0h+var_47C], 0
0x180003df3  mov     [rdx], rax
0x180003df6  lea     r14, [rcx+38h]
0x180003dfa  mov     r8, [rcx+50h]; unsigned __int16 *
0x180003dfe  xorps   xmm0, xmm0
0x180003e01  mov     [rsp+4C0h+var_458], rax
0x180003e06  mov     r15, rdx
0x180003e09  mov     rdx, [rcx+48h]; unsigned __int16 *
0x180003e0d  lea     rax, [rsp+4C0h+var_480]
0x180003e12  mov     rdi, rcx
0x180003e15  mov     [rsp+4C0h+var_498], rax; unsigned int *
0x180003e1a  mov     r9d, 1; unsigned int
0x180003e20  mov     [rsp+4C0h+var_4A0], r14; struct IMSAdminBaseW **
0x180003e25  add     rcx, 20h ; ' '; this
0x180003e29  mov     [rsp+4C0h+var_480], 0
0x180003e31  movups  [rsp+4C0h+var_478], xmm0
0x180003e36  movups  [rsp+4C0h+var_468], xmm0
0x180003e3b  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x180003e40  mov     ebx, eax
0x180003e42  test    eax, eax
0x180003e44  js      loc_180003FA2
0x180003e4a  mov     r10, [r14]
0x180003e4d  lea     r9, [rbp+3C0h+var_240]
0x180003e54  mov     ecx, [rdi+10h]
0x180003e57  lea     r8, psz
0x180003e5e  mov     edx, [rsp+4C0h+var_480]
0x180003e62  mov     dword ptr [rsp+4C0h+var_4A0], ecx
0x180003e66  mov     rcx, r10
0x180003e69  mov     rax, [r10]
0x180003e6c  mov     rax, [rax+30h]
0x180003e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e75  mov     ebx, eax
0x180003e77  test    eax, eax
0x180003e79  js      loc_180003FA2
0x180003e7f  mov     rcx, [r14]
0x180003e82  lea     rdx, [rsp+4C0h+var_47C]
0x180003e87  lea     rax, [rsp+4C0h+Destination]
0x180003e8c  mov     dword ptr [rsp+4C0h+var_478], 3EAh
0x180003e94  mov     qword ptr [rsp+4C0h+var_468+8], rax
0x180003e99  lea     r9, [rsp+4C0h+var_478]
0x180003e9e  mov     dword ptr [rsp+4C0h+var_478+0Ch], 2
0x180003ea6  lea     r8, [rbp+3C0h+var_240]
0x180003ead  mov     qword ptr [rsp+4C0h+var_478+4], 1
0x180003eb6  mov     dword ptr [rsp+4C0h+var_468], 104h
0x180003ebe  mov     rax, [rcx]
0x180003ec1  mov     [rsp+4C0h+var_4A0], rdx
0x180003ec6  mov     edx, [rsp+4C0h+var_480]
0x180003eca  mov     rax, [rax+50h]
0x180003ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed3  mov     ebx, eax
0x180003ed5  test    eax, eax
0x180003ed7  jns     short loc_180003F38
0x180003ed9  cmp     eax, 800CC801h
0x180003ede  jnz     loc_180003FA2
0x180003ee4  mov     rcx, [rdi+50h]; String
0x180003ee8  call    cs:__imp__wcsupr
0x180003eee  mov     rcx, [rdi+50h]; Str
0x180003ef2  lea     rdx, aW3svc; "W3SVC"
0x180003ef9  call    cs:__imp_wcsstr
0x180003eff  test    rax, rax
0x180003f02  jz      short loc_180003F13
0x180003f04  mov     r9d, 20h ; ' '
0x180003f0a  lea     r8, aIiswebdirector_1; "IIsWebDirectory"
0x180003f11  jmp     short loc_180003F5A
0x180003f13  mov     rcx, [rdi+50h]; Str
0x180003f17  lea     rdx, aMsftpsvc; "MSFTPSVC"
0x180003f1e  call    cs:__imp_wcsstr
0x180003f24  test    rax, rax
0x180003f27  jz      short loc_180003F4D
0x180003f29  mov     r9d, 22h ; '"'
0x180003f2f  lea     r8, aIisftpvirtuald; "IIsFtpVirtualDir"
0x180003f36  jmp     short loc_180003F5A
0x180003f38  mov     rcx, [rdi+40h]; this
0x180003f3c  lea     rdx, [rsp+4C0h+Destination]; unsigned __int16 *
0x180003f41  call    ?ValidateClassName@IIsSchema@@QEAAJPEBG@Z; IIsSchema::ValidateClassName(ushort const *)
0x180003f46  cmp     eax, 8000500Fh
0x180003f4b  jnz     short loc_180003F6A
0x180003f4d  mov     r9d, 14h; SourceSize
0x180003f53  lea     r8, aIisobject; "IIsObject"
0x180003f5a  mov     edx, 208h; DestinationSize
0x180003f5f  lea     rcx, [rsp+4C0h+Destination]; Destination
0x180003f64  call    cs:__imp_memcpy_s
0x180003f6a  mov     ecx, 1
0x180003f6f  mov     [rsp+4C0h+var_490], r15; void **
0x180003f74  add     [rdi+10h], ecx
0x180003f77  lea     rax, IID_IDispatch
0x180003f7e  mov     [rsp+4C0h+var_498], rax; struct _GUID *
0x180003f83  lea     r9, [rdi+20h]; struct CCredentials *
0x180003f87  mov     dword ptr [rsp+4C0h+var_4A0], ecx; unsigned int
0x180003f8b  lea     r8, [rsp+4C0h+Destination]; unsigned __int16 *
0x180003f90  mov     rcx, [rdi+18h]; unsigned __int16 *
0x180003f94  lea     rdx, [rbp+3C0h+var_240]; unsigned __int16 *
0x180003f9b  call    ?CreateGenericObject@CIISGenObject@@SAJPEBG00AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z; CIISGenObject::CreateGenericObject(ushort const *,ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)
0x180003fa0  mov     ebx, eax
0x180003fa2  mov     rcx, [r14]; struct IMSAdminBaseW *
0x180003fa5  test    rcx, rcx
0x180003fa8  jz      short loc_180003FBA
0x180003faa  cmp     [rsp+4C0h+var_480], 0
0x180003faf  jz      short loc_180003FBA
0x180003fb1  mov     edx, [rsp+4C0h+var_480]; unsigned int
0x180003fb5  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x180003fba  mov     eax, 1
0x180003fbf  test    ebx, ebx
0x180003fc1  cmovs   ebx, eax
0x180003fc4  mov     eax, ebx
0x180003fc6  mov     rcx, [rbp+3C0h+var_30]
0x180003fcd  xor     rcx, rsp; StackCookie
0x180003fd0  call    __security_check_cookie
0x180003fd5  mov     rbx, [rsp+4C0h+arg_10]
0x180003fdd  add     rsp, 4A0h
0x180003fe4  pop     r15
0x180003fe6  pop     r14
0x180003fe8  pop     r12
0x180003fea  pop     rdi
0x180003feb  pop     rbp
0x180003fec  retn
```

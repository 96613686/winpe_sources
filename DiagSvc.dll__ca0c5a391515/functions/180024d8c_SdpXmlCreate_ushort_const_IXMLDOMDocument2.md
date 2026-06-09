# SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x180024d8c`
- end: `0x180024f0d`
- name: `?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021270`

## callees

- `0x180024ce8`
- `0x180024d8c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024e13`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024e13`
- `OLEAUT32!__imp_SysAllocString` at `0x180024e51`
- `OLEAUT32!__imp_SysAllocString` at `0x180024e51`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ef2`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ef2`

## string_xrefs

- `0x180024dcb`: `SdpXmlCreate`

## pseudocode

```c
__int64 __fastcall SdpXmlCreate(OLECHAR *psz, LPVOID *a2)
{
  OLECHAR *v4; // rdi
  __int64 v5; // r9
  HRESULT v6; // eax
  unsigned int v7; // ebx
  BSTR v8; // rax
  LPVOID v9; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-28h]
  __int16 v12; // [rsp+50h] [rbp+8h] BYREF
  LPVOID v13; // [rsp+60h] [rbp+18h] BYREF

  v12 = -1;
  v13 = 0;
  v4 = 0;
  if ( !psz )
  {
    v5 = 190;
LABEL_3:
    v6 = -2147024809;
    v7 = -2147024809;
LABEL_4:
    LODWORD(ppv) = v6;
LABEL_5:
    SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlCreate", v5, ppv);
    goto LABEL_19;
  }
  if ( !a2 )
  {
    v5 = 191;
    goto LABEL_3;
  }
  v6 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &v13);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 198;
    goto LABEL_4;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v13 + 504LL))(v13, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 201;
    goto LABEL_4;
  }
  v8 = SysAllocString(psz);
  v4 = v8;
  if ( !v8 )
  {
    v7 = -2147024882;
    v5 = 204;
    LODWORD(ppv) = -2147024882;
    goto LABEL_5;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)v13 + 520LL))(v13, v8, &v12);
  v7 = v6;
  if ( v6 < 0 )
  {
    v5 = 207;
    goto LABEL_4;
  }
  if ( !v12 )
  {
    v7 = -2147467259;
    v5 = 208;
    LODWORD(ppv) = -2147467259;
    goto LABEL_5;
  }
  v9 = v13;
  *a2 = v13;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 8LL))(v9);
LABEL_19:
  if ( v13 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  return v7;
}

```

## disassembly

```asm
0x180024d8c  mov     [rsp+arg_8], rbx
0x180024d91  mov     [rsp+arg_18], rbp
0x180024d96  push    rsi
0x180024d97  push    rdi
0x180024d98  push    r14
0x180024d9a  sub     rsp, 30h
0x180024d9e  xor     ebp, ebp
0x180024da0  or      eax, 0FFFFFFFFh
0x180024da3  mov     [rsp+48h+arg_0], ax
0x180024da8  mov     r14, rdx
0x180024dab  mov     [rsp+48h+arg_10], rbp
0x180024db0  mov     rsi, rcx
0x180024db3  mov     edi, ebp
0x180024db5  test    rcx, rcx
0x180024db8  jnz     short loc_180024DE8
0x180024dba  mov     r9d, 0BEh
0x180024dc0  mov     eax, 80070057h
0x180024dc5  mov     ebx, eax
0x180024dc7  mov     dword ptr [rsp+48h+ppv], eax
0x180024dcb  lea     r8, aSdpxmlcreate; "SdpXmlCreate"
0x180024dd2  mov     ecx, 1; Level
0x180024dd7  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x180024dde  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x180024de3  jmp     loc_180024ECF
0x180024de8  test    r14, r14
0x180024deb  jnz     short loc_180024DF5
0x180024ded  mov     r9d, 0BFh
0x180024df3  jmp     short loc_180024DC0
0x180024df5  xor     edx, edx; pUnkOuter
0x180024df7  lea     rax, [rsp+48h+arg_10]
0x180024dfc  lea     r9, IID_IXMLDOMDocument2; riid
0x180024e03  mov     [rsp+48h+ppv], rax; ppv
0x180024e08  lea     rcx, CLSID_DOMDocument60; rclsid
0x180024e0f  lea     r8d, [rdx+15h]; dwClsContext
0x180024e13  call    cs:__imp_CoCreateInstance
0x180024e19  mov     ebx, eax
0x180024e1b  test    eax, eax
0x180024e1d  jns     short loc_180024E27
0x180024e1f  mov     r9d, 0C6h
0x180024e25  jmp     short loc_180024DC7
0x180024e27  mov     rcx, [rsp+48h+arg_10]
0x180024e2c  xor     edx, edx
0x180024e2e  mov     rax, [rcx]
0x180024e31  mov     rax, [rax+1F8h]
0x180024e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e3d  mov     ebx, eax
0x180024e3f  test    eax, eax
0x180024e41  jns     short loc_180024E4E
0x180024e43  mov     r9d, 0C9h
0x180024e49  jmp     loc_180024DC7
0x180024e4e  mov     rcx, rsi; psz
0x180024e51  call    cs:__imp_SysAllocString
0x180024e57  mov     rdi, rax
0x180024e5a  test    rax, rax
0x180024e5d  jnz     short loc_180024E73
0x180024e5f  mov     ebx, 8007000Eh
0x180024e64  mov     r9d, 0CCh
0x180024e6a  mov     dword ptr [rsp+48h+ppv], ebx
0x180024e6e  jmp     loc_180024DCB
0x180024e73  mov     rcx, [rsp+48h+arg_10]
0x180024e78  lea     r8, [rsp+48h+arg_0]
0x180024e7d  mov     rdx, rdi
0x180024e80  mov     rax, [rcx]
0x180024e83  mov     rax, [rax+208h]
0x180024e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e8f  mov     ebx, eax
0x180024e91  test    eax, eax
0x180024e93  jns     short loc_180024EA0
0x180024e95  mov     r9d, 0CFh
0x180024e9b  jmp     loc_180024DC7
0x180024ea0  cmp     [rsp+48h+arg_0], bp
0x180024ea5  jnz     short loc_180024EBB
0x180024ea7  mov     ebx, 80004005h
0x180024eac  mov     r9d, 0D0h
0x180024eb2  mov     dword ptr [rsp+48h+ppv], ebx
0x180024eb6  jmp     loc_180024DCB
0x180024ebb  mov     rcx, [rsp+48h+arg_10]
0x180024ec0  mov     [r14], rcx
0x180024ec3  mov     rax, [rcx]
0x180024ec6  mov     rax, [rax+8]
0x180024eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ecf  mov     rcx, [rsp+48h+arg_10]
0x180024ed4  test    rcx, rcx
0x180024ed7  jz      short loc_180024EEA
0x180024ed9  mov     rax, [rcx]
0x180024edc  mov     rax, [rax+10h]
0x180024ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ee5  mov     [rsp+48h+arg_10], rbp
0x180024eea  test    rdi, rdi
0x180024eed  jz      short loc_180024EF8
0x180024eef  mov     rcx, rdi; bstrString
0x180024ef2  call    cs:__imp_SysFreeString
0x180024ef8  mov     rbp, [rsp+48h+arg_18]
0x180024efd  mov     eax, ebx
0x180024eff  mov     rbx, [rsp+48h+arg_8]
0x180024f04  add     rsp, 30h
0x180024f08  pop     r14
0x180024f0a  pop     rdi
0x180024f0b  pop     rsi
0x180024f0c  retn
```

# Windows::Sms::Common::CSmsUtil::GetXmlDocument(ushort const *,IXMLDOMDocument * *)

- ea: `0x180015aac`
- end: `0x180015c72`
- name: `?GetXmlDocument@CSmsUtil@Common@Sms@Windows@@SAJPEBGPEAPEAUIXMLDOMDocument@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXMLDOMDocument **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016e74`
- `0x18001d548`
- `0x180036650`

## callees

- `0x180015aac`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015aee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015aee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Sms::Common::CSmsUtil::GetXmlDocument(const unsigned __int16 *a1, LPVOID *a2)
{
  HRESULT v4; // ebx
  __int16 v6; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  v6 = 0;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v4 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  if ( !a1 )
    goto LABEL_30;
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  if ( v4 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  if ( v4 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
  if ( v4 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
  if ( v4 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, a1, &v6);
  if ( v4 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  if ( v6 == -1 )
  {
LABEL_30:
    *a2 = ppv;
    return 0;
  }
  else
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180015aac  mov     [rsp-18h+arg_0], rbx
0x180015ab1  mov     [rsp-18h+arg_8], rsi
0x180015ab6  push    rbp
0x180015ab7  push    rdi
0x180015ab8  push    r14
0x180015aba  mov     rbp, rsp
0x180015abd  sub     rsp, 30h
0x180015ac1  mov     rsi, rdx
0x180015ac4  mov     rdi, rcx
0x180015ac7  xor     eax, eax
0x180015ac9  mov     [rbp+arg_10], ax
0x180015acd  mov     [rbp+arg_18], rax
0x180015ad1  lea     rax, [rbp+arg_18]
0x180015ad5  mov     [rsp+30h+ppv], rax; ppv
0x180015ada  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180015ae1  xor     edx, edx; pUnkOuter
0x180015ae3  lea     r8d, [rdx+17h]; dwClsContext
0x180015ae7  lea     rcx, CLSID_DOMDocument60; rclsid
0x180015aee  call    cs:__imp_CoCreateInstance
0x180015af4  mov     ebx, eax
0x180015af6  test    eax, eax
0x180015af8  jns     short loc_180015B17
0x180015afa  mov     rcx, [rbp+arg_18]
0x180015afe  test    rcx, rcx
0x180015b01  jz      short loc_180015B10
0x180015b03  mov     rdx, [rcx]
0x180015b06  mov     rax, [rdx+10h]
0x180015b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b0f  nop
0x180015b10  mov     eax, ebx
0x180015b12  jmp     loc_180015C5F
0x180015b17  test    rdi, rdi
0x180015b1a  jz      loc_180015C56
0x180015b20  mov     rcx, [rbp+arg_18]
0x180015b24  mov     rax, [rcx]
0x180015b27  xor     edx, edx
0x180015b29  mov     rax, [rax+1F8h]
0x180015b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b35  mov     ebx, eax
0x180015b37  test    eax, eax
0x180015b39  jns     short loc_180015B53
0x180015b3b  mov     rcx, [rbp+arg_18]
0x180015b3f  test    rcx, rcx
0x180015b42  jz      short loc_180015B51
0x180015b44  mov     rdx, [rcx]
0x180015b47  mov     rax, [rdx+10h]
0x180015b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b50  nop
0x180015b51  jmp     short loc_180015B10
0x180015b53  mov     rcx, [rbp+arg_18]
0x180015b57  mov     rax, [rcx]
0x180015b5a  xor     edx, edx
0x180015b5c  mov     rax, [rax+220h]
0x180015b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b68  mov     ebx, eax
0x180015b6a  test    eax, eax
0x180015b6c  jns     short loc_180015B86
0x180015b6e  mov     rcx, [rbp+arg_18]
0x180015b72  test    rcx, rcx
0x180015b75  jz      short loc_180015B84
0x180015b77  mov     rdx, [rcx]
0x180015b7a  mov     rax, [rdx+10h]
0x180015b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b83  nop
0x180015b84  jmp     short loc_180015B10
0x180015b86  mov     rcx, [rbp+arg_18]
0x180015b8a  mov     rax, [rcx]
0x180015b8d  xor     edx, edx
0x180015b8f  mov     rax, [rax+230h]
0x180015b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b9b  mov     ebx, eax
0x180015b9d  test    eax, eax
0x180015b9f  jns     short loc_180015BBC
0x180015ba1  mov     rcx, [rbp+arg_18]
0x180015ba5  test    rcx, rcx
0x180015ba8  jz      short loc_180015BB7
0x180015baa  mov     rdx, [rcx]
0x180015bad  mov     rax, [rdx+10h]
0x180015bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bb6  nop
0x180015bb7  jmp     loc_180015B10
0x180015bbc  mov     rcx, [rbp+arg_18]
0x180015bc0  mov     rax, [rcx]
0x180015bc3  or      r14d, 0FFFFFFFFh
0x180015bc7  mov     edx, r14d
0x180015bca  mov     rax, [rax+240h]
0x180015bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bd6  mov     ebx, eax
0x180015bd8  test    eax, eax
0x180015bda  jns     short loc_180015BF7
0x180015bdc  mov     rcx, [rbp+arg_18]
0x180015be0  test    rcx, rcx
0x180015be3  jz      short loc_180015BF2
0x180015be5  mov     rdx, [rcx]
0x180015be8  mov     rax, [rdx+10h]
0x180015bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bf1  nop
0x180015bf2  jmp     loc_180015B10
0x180015bf7  mov     rcx, [rbp+arg_18]
0x180015bfb  mov     rax, [rcx]
0x180015bfe  lea     r8, [rbp+arg_10]
0x180015c02  mov     rdx, rdi
0x180015c05  mov     rax, [rax+208h]
0x180015c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c11  mov     ebx, eax
0x180015c13  test    eax, eax
0x180015c15  jns     short loc_180015C32
0x180015c17  mov     rcx, [rbp+arg_18]
0x180015c1b  test    rcx, rcx
0x180015c1e  jz      short loc_180015C2D
0x180015c20  mov     rdx, [rcx]
0x180015c23  mov     rax, [rdx+10h]
0x180015c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c2c  nop
0x180015c2d  jmp     loc_180015B10
0x180015c32  cmp     [rbp+arg_10], r14w
0x180015c37  jz      short loc_180015C56
0x180015c39  mov     rcx, [rbp+arg_18]
0x180015c3d  test    rcx, rcx
0x180015c40  jz      short loc_180015C4F
0x180015c42  mov     rax, [rcx]
0x180015c45  mov     rax, [rax+10h]
0x180015c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c4e  nop
0x180015c4f  mov     eax, 80004005h
0x180015c54  jmp     short loc_180015C5F
0x180015c56  mov     rax, [rbp+arg_18]
0x180015c5a  mov     [rsi], rax
0x180015c5d  xor     eax, eax
0x180015c5f  mov     rbx, [rsp+30h+arg_0]
0x180015c64  mov     rsi, [rsp+30h+arg_8]
0x180015c69  add     rsp, 30h
0x180015c6d  pop     r14
0x180015c6f  pop     rdi
0x180015c70  pop     rbp
0x180015c71  retn
```

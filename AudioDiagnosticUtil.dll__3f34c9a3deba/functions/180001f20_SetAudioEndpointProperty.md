# SetAudioEndpointProperty

- ea: `0x180001f20`
- end: `0x18000205b`
- name: `SetAudioEndpointProperty`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f20`
- `0x180003010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001f70`
- `ole32!CoCreateInstance` at `0x180001f70`
- `ole32!PropVariantClear` at `0x180001ff3`
- `ole32!PropVariantClear` at `0x180001ff3`

## pseudocode

```c
__int64 __fastcall SetAudioEndpointProperty(__int64 a1)
{
  HRESULT v2; // ebx
  void (*v3)(void); // rax
  PROPVARIANT pvar; // [rsp+30h] [rbp-20h] BYREF
  __int64 v6; // [rsp+78h] [rbp+28h] BYREF
  __int64 v7; // [rsp+80h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+38h] BYREF

  ppv = 0;
  v7 = 0;
  v6 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v2 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         0x17u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &ppv);
  if ( v2 < 0
    || (v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, a1, &v7), v2 < 0)
    || (v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 32LL))(v7, 2, &v6), v2 < 0) )
  {
    if ( !v6 )
      goto LABEL_9;
    v3 = *(void (**)(void))(*(_QWORD *)v6 + 16LL);
  }
  else
  {
    pvar.vt = 11;
    pvar.iVal = -1;
    v2 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v6 + 48LL))(
           v6,
           PKEY_Endpoint_UserPreferredDriver,
           &pvar);
    PropVariantClear(&pvar);
    if ( !v6 )
      goto LABEL_9;
    v3 = *(void (**)(void))(*(_QWORD *)v6 + 16LL);
  }
  v3();
LABEL_9:
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001f20  push    rbp
0x180001f22  push    rbx
0x180001f23  push    rdi
0x180001f24  mov     rbp, rsp
0x180001f27  sub     rsp, 50h
0x180001f2b  xor     eax, eax
0x180001f2d  mov     [rbp+arg_18], 0
0x180001f35  xor     edx, edx; pUnkOuter
0x180001f37  mov     qword ptr [rbp+pvar+10h], rax
0x180001f3b  mov     rdi, rcx
0x180001f3e  mov     [rbp+arg_10], 0
0x180001f46  xorps   xmm0, xmm0
0x180001f49  mov     [rbp+arg_8], 0
0x180001f51  lea     rax, [rbp+arg_18]
0x180001f55  lea     r8d, [rdx+17h]; dwClsContext
0x180001f59  mov     [rsp+50h+ppv], rax; ppv
0x180001f5e  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180001f65  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180001f6c  movups  xmmword ptr [rbp+pvar], xmm0
0x180001f70  call    cs:__imp_CoCreateInstance
0x180001f77  nop     dword ptr [rax+rax+00h]
0x180001f7c  mov     ebx, eax
0x180001f7e  test    eax, eax
0x180001f80  js      loc_180002011
0x180001f86  mov     rcx, [rbp+arg_18]
0x180001f8a  lea     r8, [rbp+arg_10]
0x180001f8e  mov     rdx, rdi
0x180001f91  mov     rax, [rcx]
0x180001f94  mov     rax, [rax+28h]
0x180001f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f9d  mov     ebx, eax
0x180001f9f  test    eax, eax
0x180001fa1  js      short loc_180002011
0x180001fa3  mov     rcx, [rbp+arg_10]
0x180001fa7  lea     r8, [rbp+arg_8]
0x180001fab  mov     edx, 2
0x180001fb0  mov     rax, [rcx]
0x180001fb3  mov     rax, [rax+20h]
0x180001fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fbc  mov     ebx, eax
0x180001fbe  test    eax, eax
0x180001fc0  js      short loc_180002011
0x180001fc2  mov     rcx, [rbp+arg_8]
0x180001fc6  lea     r8, [rbp+pvar]
0x180001fca  mov     eax, 0Bh
0x180001fcf  lea     rdx, PKEY_Endpoint_UserPreferredDriver
0x180001fd6  mov     word ptr [rbp+pvar], ax
0x180001fda  or      eax, 0FFFFFFFFh
0x180001fdd  mov     word ptr [rbp+pvar+8], ax
0x180001fe1  mov     rax, [rcx]
0x180001fe4  mov     rax, [rax+30h]
0x180001fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fed  lea     rcx, [rbp+pvar]; pvar
0x180001ff1  mov     ebx, eax
0x180001ff3  call    cs:__imp_PropVariantClear
0x180001ffa  nop     dword ptr [rax+rax+00h]
0x180001fff  mov     rcx, [rbp+arg_8]
0x180002003  test    rcx, rcx
0x180002006  jz      short loc_180002026
0x180002008  mov     rdx, [rcx]
0x18000200b  mov     rax, [rdx+10h]
0x18000200f  jmp     short loc_180002021
0x180002011  mov     rcx, [rbp+arg_8]
0x180002015  test    rcx, rcx
0x180002018  jz      short loc_180002026
0x18000201a  mov     rax, [rcx]
0x18000201d  mov     rax, [rax+10h]
0x180002021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002026  mov     rcx, [rbp+arg_10]
0x18000202a  test    rcx, rcx
0x18000202d  jz      short loc_18000203B
0x18000202f  mov     rax, [rcx]
0x180002032  mov     rax, [rax+10h]
0x180002036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000203b  mov     rcx, [rbp+arg_18]
0x18000203f  test    rcx, rcx
0x180002042  jz      short loc_180002050
0x180002044  mov     rax, [rcx]
0x180002047  mov     rax, [rax+10h]
0x18000204b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002050  mov     eax, ebx
0x180002052  add     rsp, 50h
0x180002056  pop     rdi
0x180002057  pop     rbx
0x180002058  pop     rbp
0x180002059  retn
```

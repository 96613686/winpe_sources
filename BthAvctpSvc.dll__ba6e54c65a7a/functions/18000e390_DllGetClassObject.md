# DllGetClassObject

- ea: `0x18000e390`
- end: `0x18000e4b6`
- name: `DllGetClassObject`
- size: `294`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e390`
- `0x18000e61c`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000e4a1`
- `RPCRT4!NdrDllGetClassObject` at `0x18000e4a1`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  void **v3; // rdi
  const IID *v4; // rsi
  PVOID *v6; // rcx
  char v7; // bl
  _UNKNOWN **v8; // rax
  int pPSFactoryBuffer; // [rsp+28h] [rbp-50h]

  v3 = ppv;
  v4 = riid;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  v7 = 1;
  LOBYTE(riid) = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v8 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  LOBYTE(ppv) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 24);
  if ( (_BYTE)riid || (_BYTE)ppv )
  {
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (int)riid,
      (int)ppv,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      pPSFactoryBuffer,
      13,
      &WPP_71300114d67b3afaf3df9ec65f4e31ec_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v8 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  LOBYTE(riid) = v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u;
  if ( v8 == &WPP_RECORDER_INITIALIZED || !*((_WORD *)v6 + 24) )
    v7 = 0;
  if ( (_BYTE)riid || v7 )
  {
    LOBYTE(ppv) = v7;
    WPP_RECORDER_AND_TRACE_SF_(
      (int)v6[2],
      (int)riid,
      (int)ppv,
      (int)v6[5],
      5,
      pPSFactoryBuffer,
      14,
      &WPP_71300114d67b3afaf3df9ec65f4e31ec_Traceguids);
  }
  return NdrDllGetClassObject(
           rclsid,
           v4,
           v3,
           (const ProxyFileInfo **)&aProxyFileList,
           &CLSID_PSFactoryBuffer,
           &gPFactory);
}

```

## disassembly

```asm
0x18000e390  push    rbx
0x18000e392  push    rbp
0x18000e393  push    rsi
0x18000e394  push    rdi
0x18000e395  push    r12
0x18000e397  push    r14
0x18000e399  push    r15
0x18000e39b  sub     rsp, 40h
0x18000e39f  mov     rdi, r8
0x18000e3a2  mov     rsi, rdx
0x18000e3a5  mov     rbp, rcx
0x18000e3a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3af  lea     r14, WPP_GLOBAL_Control
0x18000e3b6  mov     bl, 1
0x18000e3b8  cmp     rcx, r14
0x18000e3bb  jz      short loc_18000E3CC
0x18000e3bd  test    [rcx+1Ch], bl
0x18000e3c0  jz      short loc_18000E3CC
0x18000e3c2  cmp     byte ptr [rcx+19h], 5
0x18000e3c6  jb      short loc_18000E3CC
0x18000e3c8  mov     dl, bl
0x18000e3ca  jmp     short loc_18000E3CE
0x18000e3cc  xor     dl, dl; int
0x18000e3ce  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000e3d5  lea     r15, WPP_RECORDER_INITIALIZED
0x18000e3dc  cmp     rax, r15
0x18000e3df  jz      short loc_18000E3ED
0x18000e3e1  cmp     word ptr [rcx+30h], 0
0x18000e3e6  jz      short loc_18000E3ED
0x18000e3e8  mov     r8b, bl
0x18000e3eb  jmp     short loc_18000E3F0
0x18000e3ed  xor     r8b, r8b; int
0x18000e3f0  lea     r12, WPP_71300114d67b3afaf3df9ec65f4e31ec_Traceguids
0x18000e3f7  test    dl, dl
0x18000e3f9  jnz     short loc_18000E400
0x18000e3fb  test    r8b, r8b
0x18000e3fe  jz      short loc_18000E42C
0x18000e400  mov     r9, [rcx+28h]; int
0x18000e404  mov     rcx, [rcx+10h]; int
0x18000e408  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x18000e40d  mov     [rsp+78h+var_48], 0Dh; __int16
0x18000e414  mov     byte ptr [rsp+78h+pclsid], 5; char
0x18000e419  call    WPP_RECORDER_AND_TRACE_SF_
0x18000e41e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e425  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000e42c  cmp     rcx, r14
0x18000e42f  jz      short loc_18000E440
0x18000e431  test    [rcx+1Ch], bl
0x18000e434  jz      short loc_18000E440
0x18000e436  cmp     byte ptr [rcx+19h], 5
0x18000e43a  jb      short loc_18000E440
0x18000e43c  mov     dl, bl
0x18000e43e  jmp     short loc_18000E442
0x18000e440  xor     dl, dl; int
0x18000e442  cmp     rax, r15
0x18000e445  jz      short loc_18000E44E
0x18000e447  cmp     word ptr [rcx+30h], 0
0x18000e44c  jnz     short loc_18000E450
0x18000e44e  xor     bl, bl
0x18000e450  test    dl, dl
0x18000e452  jnz     short loc_18000E458
0x18000e454  test    bl, bl
0x18000e456  jz      short loc_18000E479
0x18000e458  mov     r9, [rcx+28h]; int
0x18000e45c  mov     r8b, bl; int
0x18000e45f  mov     rcx, [rcx+10h]; int
0x18000e463  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x18000e468  mov     [rsp+78h+var_48], 0Eh; __int16
0x18000e46f  mov     byte ptr [rsp+78h+pclsid], 5; char
0x18000e474  call    WPP_RECORDER_AND_TRACE_SF_
0x18000e479  lea     rax, gPFactory
0x18000e480  mov     r8, rdi; ppv
0x18000e483  mov     [rsp+78h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000e488  lea     r9, aProxyFileList; pProxyFileList
0x18000e48f  lea     rax, CLSID_PSFactoryBuffer
0x18000e496  mov     rdx, rsi; riid
0x18000e499  mov     rcx, rbp; rclsid
0x18000e49c  mov     [rsp+78h+pclsid], rax; pclsid
0x18000e4a1  call    cs:__imp_NdrDllGetClassObject
0x18000e4a7  add     rsp, 40h
0x18000e4ab  pop     r15
0x18000e4ad  pop     r14
0x18000e4af  pop     r12
0x18000e4b1  pop     rdi
0x18000e4b2  pop     rsi
0x18000e4b3  pop     rbp
0x18000e4b4  pop     rbx
0x18000e4b5  retn
```

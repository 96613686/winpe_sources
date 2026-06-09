# CEnhancedStorageEnumerator::FinalConstruct(void)

- ea: `0x180001b20`
- end: `0x180001c42`
- name: `?FinalConstruct@CEnhancedStorageEnumerator@@QEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(CEnhancedStorageEnumerator *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800019d0`

## callees

- `0x180001b20`
- `0x1800064cc`
- `0x18000684c`
- `0x18000c010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001b69`
- `ole32!CoCreateInstance` at `0x180001b69`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageEnumerator::FinalConstruct(
        CEnhancedStorageEnumerator *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  ppv = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, a4);
  v5 = CoCreateInstance(&CLSID_EnumEnhancedStorageACT, 0, 1u, &GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7, &ppv);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids,
        (unsigned int)v5);
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, char *, char *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           (char *)this + 32,
           (char *)this + 28);
    v6 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids,
          (unsigned int)v7);
      *((_QWORD *)this + 4) = 0;
      *((_DWORD *)this + 7) = 0;
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v6;
}

```

## disassembly

```asm
0x180001b20  push    rbx
0x180001b22  push    rsi
0x180001b23  push    rdi
0x180001b24  push    r14
0x180001b26  sub     rsp, 38h
0x180001b2a  mov     rdi, rcx
0x180001b2d  mov     [rsp+58h+arg_8], 0
0x180001b36  lea     r14, WPP_GLOBAL_Control
0x180001b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b44  cmp     rcx, r14
0x180001b47  jnz     short loc_180001BB7
0x180001b49  lea     rax, [rsp+58h+arg_8]
0x180001b4e  mov     [rsp+58h+ppv], rax; ppv
0x180001b53  lea     r9, _GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7; riid
0x180001b5a  xor     edx, edx; pUnkOuter
0x180001b5c  mov     r8d, 1; dwClsContext
0x180001b62  lea     rcx, CLSID_EnumEnhancedStorageACT; rclsid
0x180001b69  call    cs:__imp_CoCreateInstance
0x180001b6f  mov     ebx, eax
0x180001b71  test    eax, eax
0x180001b73  js      short loc_180001BD7
0x180001b75  mov     rcx, [rsp+58h+arg_8]
0x180001b7a  mov     rax, [rcx]
0x180001b7d  lea     r8, [rdi+1Ch]
0x180001b81  lea     rdx, [rdi+20h]
0x180001b85  mov     rax, [rax+18h]
0x180001b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b8e  mov     ebx, eax
0x180001b90  test    eax, eax
0x180001b92  js      short loc_180001C03
0x180001b94  mov     rcx, [rsp+58h+arg_8]
0x180001b99  test    rcx, rcx
0x180001b9c  jz      short loc_180001BAB
0x180001b9e  mov     rax, [rcx]
0x180001ba1  mov     rax, [rax+10h]
0x180001ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001baa  nop
0x180001bab  mov     eax, ebx
0x180001bad  add     rsp, 38h
0x180001bb1  pop     r14
0x180001bb3  pop     rdi
0x180001bb4  pop     rsi
0x180001bb5  pop     rbx
0x180001bb6  retn
0x180001bb7  test    byte ptr [rcx+1Ch], 20h
0x180001bbb  jz      short loc_180001B49
0x180001bbd  mov     edx, 0Bh
0x180001bc2  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180001bc9  mov     rcx, [rcx+10h]
0x180001bcd  call    WPP_SF_
0x180001bd2  jmp     loc_180001B49
0x180001bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bde  cmp     rcx, r14
0x180001be1  jz      short loc_180001B94
0x180001be3  test    byte ptr [rcx+1Ch], 2
0x180001be7  jz      short loc_180001B94
0x180001be9  mov     edx, 0Ch
0x180001bee  mov     r9d, eax
0x180001bf1  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180001bf8  mov     rcx, [rcx+10h]
0x180001bfc  call    WPP_SF_d
0x180001c01  jmp     short loc_180001B94
0x180001c03  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c0a  cmp     rcx, r14
0x180001c0d  jz      short loc_180001C2D
0x180001c0f  test    byte ptr [rcx+1Ch], 2
0x180001c13  jz      short loc_180001C2D
0x180001c15  mov     edx, 0Dh
0x180001c1a  mov     r9d, eax
0x180001c1d  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180001c24  mov     rcx, [rcx+10h]
0x180001c28  call    WPP_SF_d
0x180001c2d  mov     qword ptr [rdi+20h], 0
0x180001c35  mov     dword ptr [rdi+1Ch], 0
0x180001c3c  jmp     loc_180001B94
```

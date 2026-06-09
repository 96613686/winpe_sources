# CImpIADOSecurity::SecurityDialog(IUnknown *,ushort const *,ushort const *,ushort const *)

- ea: `0x180029760`
- end: `0x18002981f`
- name: `?SecurityDialog@CImpIADOSecurity@@UEAAJPEAUIUnknown@@PEBG11@Z`
- size: `191`
- prototype: `int(CImpIADOSecurity *__hidden this, struct IUnknown *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029760`
- `0x180029a14`
- `0x180029b14`
- `0x180029bf8`

## import_xrefs

- `USER32!MessageBoxW` at `0x1800297fb`
- `USER32!MessageBoxW` at `0x1800297fb`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::SecurityDialog(
        CImpIADOSecurity *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpCaption)
{
  __int64 result; // rax
  CImpIADOSecurity *v8; // rcx
  CImpIADOSecurity *v9; // rcx
  HWND WindowHandle; // rax
  __int64 v11; // rcx
  unsigned int v12; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v13[5]; // [rsp+24h] [rbp-14h] BYREF

  v12 = 0;
  v13[0] = 0;
  result = CImpIADOSecurity::getZone(this, a3, &v12, 0);
  if ( (int)result >= 0 )
  {
    result = CImpIADOSecurity::getPolicy(v8, v12, v13);
    if ( (int)result >= 0 )
    {
      if ( v13[0] )
      {
        if ( v13[0] != 1 )
        {
          if ( v13[0] != 3 )
            return 2147500037LL;
          return 1;
        }
        if ( !a2 )
          return 1;
        WindowHandle = CImpIADOSecurity::getWindowHandle(v9, a2);
        if ( !a4 )
          return 1;
        if ( !lpCaption )
          return 1;
        v11 = -1;
        do
          ++v11;
        while ( a4[v11] );
        if ( !v11 || MessageBoxW(WindowHandle, a4, lpCaption, 0x2034u) != 6 )
          return 1;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029760  mov     [rsp+arg_0], rbx
0x180029765  mov     [rsp+arg_8], rsi
0x18002976a  push    rdi
0x18002976b  sub     rsp, 30h
0x18002976f  mov     rax, r8
0x180029772  mov     rdi, r9
0x180029775  mov     rbx, rdx
0x180029778  lea     r8, [rsp+38h+var_18]; unsigned int *
0x18002977d  xor     esi, esi
0x18002977f  mov     rdx, rax; unsigned __int16 *
0x180029782  xor     r9d, r9d; struct IInternetSecurityManager **
0x180029785  mov     [rsp+38h+var_18], esi
0x180029789  mov     [rsp+38h+var_14], esi
0x18002978d  call    ?getZone@CImpIADOSecurity@@AEAAJPEBGPEAKPEAPEAUIInternetSecurityManager@@@Z; CImpIADOSecurity::getZone(ushort const *,ulong *,IInternetSecurityManager * *)
0x180029792  test    eax, eax
0x180029794  js      short loc_18002980F
0x180029796  mov     edx, [rsp+38h+var_18]; unsigned int
0x18002979a  lea     r8, [rsp+38h+var_14]; unsigned int *
0x18002979f  call    ?getPolicy@CImpIADOSecurity@@AEAAJKPEAK@Z; CImpIADOSecurity::getPolicy(ulong,ulong *)
0x1800297a4  test    eax, eax
0x1800297a6  js      short loc_18002980F
0x1800297a8  mov     eax, [rsp+38h+var_14]
0x1800297ac  test    eax, eax
0x1800297ae  jz      short loc_18002980D
0x1800297b0  sub     eax, 1
0x1800297b3  jz      short loc_1800297C1
0x1800297b5  cmp     eax, 2
0x1800297b8  jz      short loc_180029806
0x1800297ba  mov     eax, 80004005h
0x1800297bf  jmp     short loc_18002980F
0x1800297c1  test    rbx, rbx
0x1800297c4  jz      short loc_180029806
0x1800297c6  mov     rdx, rbx; struct IUnknown *
0x1800297c9  call    ?getWindowHandle@CImpIADOSecurity@@AEAAPEAUHWND__@@PEAUIUnknown@@@Z; CImpIADOSecurity::getWindowHandle(IUnknown *)
0x1800297ce  test    rdi, rdi
0x1800297d1  jz      short loc_180029806
0x1800297d3  mov     r8, [rsp+38h+lpCaption]; lpCaption
0x1800297d8  test    r8, r8
0x1800297db  jz      short loc_180029806
0x1800297dd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800297e1  inc     rcx
0x1800297e4  cmp     [rdi+rcx*2], si
0x1800297e8  jnz     short loc_1800297E1
0x1800297ea  test    rcx, rcx
0x1800297ed  jz      short loc_180029806
0x1800297ef  mov     r9d, 2034h; uType
0x1800297f5  mov     rdx, rdi; lpText
0x1800297f8  mov     rcx, rax; hWnd
0x1800297fb  call    cs:__imp_MessageBoxW
0x180029801  cmp     eax, 6
0x180029804  jz      short loc_18002980D
0x180029806  mov     eax, 1
0x18002980b  jmp     short loc_18002980F
0x18002980d  xor     eax, eax
0x18002980f  mov     rbx, [rsp+38h+arg_0]
0x180029814  mov     rsi, [rsp+38h+arg_8]
0x180029819  add     rsp, 30h
0x18002981d  pop     rdi
0x18002981e  retn
```

# FwInitPortCollCache(_tag_FW_PORT_COLLECTION_TYPE)

- ea: `0x18001f3cc`
- end: `0x18001f4ad`
- name: `?FwInitPortCollCache@@YAKW4_tag_FW_PORT_COLLECTION_TYPE@@@Z`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000fe30`

## callees

- `0x180005954`
- `0x18001f3cc`
- `0x1800277b0`

## import_xrefs

- `fwbase!FwIOReadPortUseIndications` at `0x18001f41c`
- `fwbase!FwIOReadPortUseIndications` at `0x18001f41c`
- `fwbase!FwBaseFree` at `0x18001f488`
- `fwbase!FwBaseFree` at `0x18001f488`
- `fwbase!FwHResultToWindowsError` at `0x18001f490`
- `fwbase!FwHResultToWindowsError` at `0x18001f490`

## pseudocode

```c
__int64 __fastcall FwInitPortCollCache(__int64 a1)
{
  int v1; // ebx
  __int64 v2; // rsi
  struct _tag_FW_PORT_COLLECTION_CACHE near **v3; // rdi
  __int64 i; // r9
  __int64 v6; // [rsp+20h] [rbp-38h] BYREF

  v1 = 0;
  v6 = 0;
  if ( !dword_1800983A0 )
  {
    v2 = 2LL * (int)a1;
    dword_1800983A0 = 1;
    v3 = &PortCollCache + 2 * (int)a1;
    v1 = FwIOReadPortUseIndications(a1, &v6, v3 + 1);
    if ( v1 >= 0 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)v3 + 2); i = (unsigned int)(i + 1) )
        *((_DWORD *)*(&PortCollCache + v2) + i) = *(_DWORD *)(v6 + 4 * i);
    }
    else if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids,
        (unsigned int)v1);
    }
    if ( v6 )
      FwBaseFree(v6);
  }
  return FwHResultToWindowsError((unsigned int)v1);
}

```

## disassembly

```asm
0x18001f3cc  push    rbx
0x18001f3ce  push    rsi
0x18001f3cf  push    rdi
0x18001f3d0  push    r14
0x18001f3d2  sub     rsp, 38h
0x18001f3d6  mov     rax, cs:__security_cookie
0x18001f3dd  xor     rax, rsp
0x18001f3e0  mov     [rsp+58h+var_30], rax
0x18001f3e5  xor     ebx, ebx
0x18001f3e7  cmp     cs:dword_1800983A0, ebx
0x18001f3ed  mov     [rsp+58h+var_38], rbx
0x18001f3f2  jnz     loc_18001F48E
0x18001f3f8  movsxd  rsi, ecx
0x18001f3fb  lea     r14, ?PortCollCache@@3PAU_tag_FW_PORT_COLLECTION_CACHE@@A; _tag_FW_PORT_COLLECTION_CACHE near * PortCollCache
0x18001f402  add     rsi, rsi
0x18001f405  mov     cs:dword_1800983A0, 1
0x18001f40f  lea     rdx, [rsp+58h+var_38]
0x18001f414  lea     rdi, [r14+rsi*8]
0x18001f418  lea     r8, [rdi+8]
0x18001f41c  call    cs:__imp_FwIOReadPortUseIndications
0x18001f422  mov     ebx, eax
0x18001f424  test    eax, eax
0x18001f426  jns     short loc_18001F45B
0x18001f428  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f42f  lea     rax, WPP_GLOBAL_Control
0x18001f436  cmp     rcx, rax
0x18001f439  jz      short loc_18001F47E
0x18001f43b  test    byte ptr [rcx+1Ch], 1
0x18001f43f  jz      short loc_18001F47E
0x18001f441  mov     rcx, [rcx+10h]
0x18001f445  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x18001f44c  mov     edx, 1Dh
0x18001f451  mov     r9d, ebx
0x18001f454  call    WPP_SF_d
0x18001f459  jmp     short loc_18001F47E
0x18001f45b  xor     r9d, r9d
0x18001f45e  cmp     [rdi+8], r9d
0x18001f462  jbe     short loc_18001F47E
0x18001f464  mov     rax, [rsp+58h+var_38]
0x18001f469  mov     rdx, [r14+rsi*8]
0x18001f46d  mov     ecx, [rax+r9*4]
0x18001f471  mov     [rdx+r9*4], ecx
0x18001f475  inc     r9d
0x18001f478  cmp     r9d, [rdi+8]
0x18001f47c  jb      short loc_18001F464
0x18001f47e  mov     rcx, [rsp+58h+var_38]
0x18001f483  test    rcx, rcx
0x18001f486  jz      short loc_18001F48E
0x18001f488  call    cs:__imp_FwBaseFree
0x18001f48e  mov     ecx, ebx
0x18001f490  call    cs:__imp_FwHResultToWindowsError
0x18001f496  mov     rcx, [rsp+58h+var_30]
0x18001f49b  xor     rcx, rsp; StackCookie
0x18001f49e  call    __security_check_cookie
0x18001f4a3  add     rsp, 38h
0x18001f4a7  pop     r14
0x18001f4a9  pop     rdi
0x18001f4aa  pop     rsi
0x18001f4ab  pop     rbx
0x18001f4ac  retn
```

# FwParserInterfaceID(ushort const *,_tag_FW_INTERFACE_LUIDS *)

- ea: `0x180018314`
- end: `0x1800183e5`
- name: `?FwParserInterfaceID@@YAJPEBGPEAU_tag_FW_INTERFACE_LUIDS@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, const void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018300`
- `0x180025a20`

## callees

- `0x1800042c4`
- `0x180018314`
- `0x180039bb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018391`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018391`
- `fwbase!FwFree` at `0x1800183c1`
- `fwbase!FwFree` at `0x1800183d2`
- `fwbase!FwFree` at `0x1800183c1`
- `fwbase!FwFree` at `0x1800183d2`
- `fwbase!FwAlloc` at `0x180018330`
- `fwbase!FwAlloc` at `0x180018330`

## pseudocode

```c
__int64 __fastcall FwParserInterfaceID(LPCOLESTR lpsz, const void **a2)
{
  __int64 v2; // rbx
  int v5; // ebp
  GUID *v6; // rax
  GUID *v7; // rsi
  HRESULT v8; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx

  v2 = *(unsigned int *)a2;
  v5 = v2 + 1;
  v6 = (GUID *)FwAlloc(16LL * (unsigned int)(v2 + 1));
  v7 = v6;
  if ( v6 )
  {
    memcpy_0(v6, a2[1], 16LL * *(unsigned int *)a2);
    v8 = CLSIDFromString(lpsz, &v7[v2]);
    if ( v8 >= 0 )
    {
      FwFree(a2[1]);
      a2[1] = v7;
      v7 = 0;
      *(_DWORD *)a2 = v5;
      goto LABEL_11;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 39;
      goto LABEL_5;
    }
  }
  else
  {
    v8 = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 38;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, (unsigned int)v8);
    }
  }
LABEL_11:
  FwFree(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018314  push    rbx
0x180018316  push    rbp
0x180018317  push    rsi
0x180018318  push    rdi
0x180018319  push    r14
0x18001831b  sub     rsp, 20h
0x18001831f  mov     ebx, [rdx]
0x180018321  mov     r14, rcx
0x180018324  mov     rdi, rdx
0x180018327  lea     ebp, [rbx+1]
0x18001832a  mov     ecx, ebp
0x18001832c  shl     rcx, 4
0x180018330  call    cs:__imp_FwAlloc
0x180018336  mov     rsi, rax
0x180018339  test    rax, rax
0x18001833c  jnz     short loc_180018374
0x18001833e  mov     ebx, 8007000Eh
0x180018343  mov     rcx, cs:WPP_GLOBAL_Control
0x18001834a  lea     rax, WPP_GLOBAL_Control
0x180018351  cmp     rcx, rax
0x180018354  jz      short loc_1800183CF
0x180018356  test    byte ptr [rcx+1Ch], 1
0x18001835a  jz      short loc_1800183CF
0x18001835c  lea     edx, [rsi+26h]
0x18001835f  mov     rcx, [rcx+10h]
0x180018363  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x18001836a  mov     r9d, ebx
0x18001836d  call    WPP_SF_d
0x180018372  jmp     short loc_1800183CF
0x180018374  mov     r8d, [rdi]
0x180018377  mov     rcx, rsi; void *
0x18001837a  mov     rdx, [rdi+8]; Src
0x18001837e  shl     r8, 4; Size
0x180018382  call    memcpy_0
0x180018387  add     rbx, rbx
0x18001838a  mov     rcx, r14; lpsz
0x18001838d  lea     rdx, [rsi+rbx*8]; pclsid
0x180018391  call    cs:__imp_CLSIDFromString
0x180018397  mov     ebx, eax
0x180018399  test    eax, eax
0x18001839b  jns     short loc_1800183BD
0x18001839d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183a4  lea     rax, WPP_GLOBAL_Control
0x1800183ab  cmp     rcx, rax
0x1800183ae  jz      short loc_1800183CF
0x1800183b0  test    byte ptr [rcx+1Ch], 1
0x1800183b4  jz      short loc_1800183CF
0x1800183b6  mov     edx, 27h ; '''
0x1800183bb  jmp     short loc_18001835F
0x1800183bd  mov     rcx, [rdi+8]
0x1800183c1  call    cs:__imp_FwFree
0x1800183c7  mov     [rdi+8], rsi
0x1800183cb  xor     esi, esi
0x1800183cd  mov     [rdi], ebp
0x1800183cf  mov     rcx, rsi
0x1800183d2  call    cs:__imp_FwFree
0x1800183d8  mov     eax, ebx
0x1800183da  add     rsp, 20h
0x1800183de  pop     r14
0x1800183e0  pop     rdi
0x1800183e1  pop     rsi
0x1800183e2  pop     rbp
0x1800183e3  pop     rbx
0x1800183e4  retn
```

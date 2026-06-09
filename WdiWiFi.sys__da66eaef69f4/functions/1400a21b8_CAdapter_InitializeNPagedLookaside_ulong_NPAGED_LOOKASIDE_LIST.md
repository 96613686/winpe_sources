# CAdapter::InitializeNPagedLookaside(ulong,_NPAGED_LOOKASIDE_LIST *)

- ea: `0x1400a21b8`
- end: `0x1400a2292`
- name: `?InitializeNPagedLookaside@CAdapter@@AEAAXKPEAU_NPAGED_LOOKASIDE_LIST@@@Z`
- size: `218`
- prototype: `void(CAdapter *__hidden this, unsigned int, struct _NPAGED_LOOKASIDE_LIST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400a38f8`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x1400a21b8`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a223d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400a223d`
- `NDIS!NdisGetVersion` at `0x1400a2211`
- `NDIS!NdisGetVersion` at `0x1400a2211`

## pseudocode

```c
void __fastcall CAdapter::InitializeNPagedLookaside(CAdapter *this, unsigned int a2, struct _NPAGED_LOOKASIDE_LIST *a3)
{
  SIZE_T Size; // rdi
  int v5; // edx
  __int64 Tag; // [rsp+28h] [rbp-40h]

  Size = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      233,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  NdisGetVersion();
  ExInitializeNPagedLookasideList(a3, 0, 0, 0x200u, Size, 0x44696457u, 0);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(Tag) = 0;
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      234,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      Tag);
  }
}

```

## disassembly

```asm
0x1400a21b8  push    rbx
0x1400a21ba  push    rsi
0x1400a21bb  push    rdi
0x1400a21bc  push    r14
0x1400a21be  push    r15
0x1400a21c0  sub     rsp, 40h
0x1400a21c4  mov     rbx, r8
0x1400a21c7  mov     edi, edx
0x1400a21c9  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a21d0  xor     esi, esi
0x1400a21d2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400a21d9  lea     r14, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a21e0  jz      short loc_1400A2211
0x1400a21e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a21e9  cmp     byte ptr [rcx+29h], 5
0x1400a21ed  jnb     short loc_1400A21F5
0x1400a21ef  cmp     [rcx+48h], si
0x1400a21f3  jz      short loc_1400A2211
0x1400a21f5  mov     rcx, [rcx+40h]
0x1400a21f9  mov     r9d, 0E9h
0x1400a21ff  mov     r8d, 1
0x1400a2205  mov     [rsp+68h+Size], r14
0x1400a220a  mov     dl, 5
0x1400a220c  call    WPP_RECORDER_SF_
0x1400a2211  call    cs:__imp_NdisGetVersion
0x1400a2218  nop     dword ptr [rax+rax+00h]
0x1400a221d  mov     [rsp+68h+Depth], si; Depth
0x1400a2222  mov     r9d, 200h; Flags
0x1400a2228  mov     dword ptr [rsp+68h+Tag], 44696457h; Tag
0x1400a2230  xor     r8d, r8d; Free
0x1400a2233  xor     edx, edx; Allocate
0x1400a2235  mov     [rsp+68h+Size], rdi; Size
0x1400a223a  mov     rcx, rbx; Lookaside
0x1400a223d  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400a2244  nop     dword ptr [rax+rax+00h]
0x1400a2249  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400a2250  jz      short loc_1400A2285
0x1400a2252  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2259  cmp     byte ptr [rcx+29h], 5
0x1400a225d  jnb     short loc_1400A2265
0x1400a225f  cmp     [rcx+48h], si
0x1400a2263  jz      short loc_1400A2285
0x1400a2265  mov     rcx, [rcx+40h]
0x1400a2269  mov     r9d, 0EAh
0x1400a226f  mov     dword ptr [rsp+68h+Tag], esi
0x1400a2273  mov     r8d, 1
0x1400a2279  mov     dl, 5
0x1400a227b  mov     [rsp+68h+Size], r14
0x1400a2280  call    WPP_RECORDER_SF_D
0x1400a2285  add     rsp, 40h
0x1400a2289  pop     r15
0x1400a228b  pop     r14
0x1400a228d  pop     rdi
0x1400a228e  pop     rsi
0x1400a228f  pop     rbx
0x1400a2290  retn
```

# AdapterFreeWifiFrameMetadata(void *,_WDI_FRAME_METADATA *)

- ea: `0x140040f40`
- end: `0x140041024`
- name: `?AdapterFreeWifiFrameMetadata@@YAXPEAXPEAU_WDI_FRAME_METADATA@@@Z`
- size: `228`
- prototype: `void __fastcall(void *, struct _WDI_FRAME_METADATA *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x140040f40`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040f9e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040f9e`

## pseudocode

```c
void __fastcall AdapterFreeWifiFrameMetadata(char *a1, struct _WDI_FRAME_METADATA *a2)
{
  union _WDI_FRAME_METADATA::$BDCCB360007CCF12BE65E81280473552 *p_u; // rdi
  int v4; // [rsp+28h] [rbp-10h]

  if ( a2 )
  {
    p_u = &a2[-1].u;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        236,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
    }
    if ( p_u )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 5440), p_u);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      v4 = 0;
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        237,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        v4);
    }
  }
}

```

## disassembly

```asm
0x140040f40  test    rdx, rdx
0x140040f43  jz      locret_140040FDB
0x140040f49  push    rbx
0x140040f4a  sub     rsp, 30h
0x140040f4e  mov     [rsp+38h+arg_0], rbp
0x140040f53  mov     rbx, rcx
0x140040f56  mov     [rsp+38h+arg_8], rsi
0x140040f5b  mov     [rsp+38h+arg_10], rdi
0x140040f60  lea     rdi, [rdx-40h]
0x140040f64  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040f6b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140040f72  lea     rbp, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140040f79  jz      short loc_140040F8F
0x140040f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140040f82  cmp     byte ptr [rcx+29h], 5
0x140040f86  jnb     short loc_140041003
0x140040f88  cmp     word ptr [rcx+48h], 0
0x140040f8d  jnz     short loc_140041003
0x140040f8f  test    rdi, rdi
0x140040f92  jz      short loc_140040FAA
0x140040f94  lea     rcx, [rbx+1540h]; Lookaside
0x140040f9b  mov     rdx, rdi; Entry
0x140040f9e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140040fa5  nop     dword ptr [rax+rax+00h]
0x140040faa  mov     rdi, [rsp+38h+arg_10]
0x140040faf  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140040fb6  mov     rsi, [rsp+38h+arg_8]
0x140040fbb  jz      short loc_140040FD1
0x140040fbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140040fc4  cmp     byte ptr [rcx+29h], 5
0x140040fc8  jnb     short loc_140040FDD
0x140040fca  cmp     word ptr [rcx+48h], 0
0x140040fcf  jnz     short loc_140040FDD
0x140040fd1  mov     rbp, [rsp+38h+arg_0]
0x140040fd6  add     rsp, 30h
0x140040fda  pop     rbx
0x140040fdb  retn
0x140040fdd  mov     rcx, [rcx+40h]
0x140040fe1  mov     r9d, 0EDh
0x140040fe7  mov     [rsp+38h+var_10], 0
0x140040fef  mov     r8d, 1
0x140040ff5  mov     dl, 5
0x140040ff7  mov     [rsp+38h+var_18], rbp
0x140040ffc  call    WPP_RECORDER_SF_D
0x140041001  jmp     short loc_140040FD1
0x140041003  mov     rcx, [rcx+40h]
0x140041007  mov     r9d, 0ECh
0x14004100d  mov     r8d, 1
0x140041013  mov     [rsp+38h+var_18], rbp
0x140041018  mov     dl, 5
0x14004101a  call    WPP_RECORDER_SF_
0x14004101f  jmp     loc_140040F8F
```

# BfPostCreate

- ea: `0x14000f930`
- end: `0x14000f9bc`
- name: `BfPostCreate`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140001348`
- `0x14000f930`
- `0x14000f9c4`

## string_xrefs

- `0x14000f96a`: `onecore\base\fs\wci\bindflt\filter\create.c`

## pseudocode

```c
__int64 __fastcall BfPostCreate(__int64 a1, __int64 a2)
{
  int v3; // edx
  int v4; // edi
  int v6; // [rsp+38h] [rbp-10h]

  v4 = BfSetWriteTrackingEa(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = v4;
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        5,
        37,
        (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
        202,
        v6);
    }
    *(_DWORD *)(a1 + 24) = v4;
    *(_QWORD *)(a1 + 32) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14000f930  mov     [rsp+arg_0], rbx
0x14000f935  push    rdi
0x14000f936  sub     rsp, 40h
0x14000f93a  mov     rax, rdx
0x14000f93d  mov     rbx, rcx
0x14000f940  mov     rdx, [rdx+20h]; FileObject
0x14000f944  mov     rcx, [rax+18h]; Instance
0x14000f948  call    BfSetWriteTrackingEa
0x14000f94d  mov     edi, eax
0x14000f94f  test    eax, eax
0x14000f951  jns     short loc_14000F9AE
0x14000f953  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f95a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f961  jz      short loc_14000F9A3
0x14000f963  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f96a  lea     rax, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14000f971  mov     [rsp+48h+var_10], edi
0x14000f975  mov     r9d, 25h ; '%'
0x14000f97b  mov     [rsp+48h+var_18], 7CAh
0x14000f983  mov     dl, 2
0x14000f985  mov     [rsp+48h+var_20], rax
0x14000f98a  lea     rax, WPP_48a527b79fd4344d8b4157379f595642_Traceguids
0x14000f991  mov     rcx, [rcx+40h]
0x14000f995  lea     r8d, [r9-20h]
0x14000f999  mov     [rsp+48h+var_28], rax
0x14000f99e  call    WPP_RECORDER_SF_sDd
0x14000f9a3  mov     [rbx+18h], edi
0x14000f9a6  mov     qword ptr [rbx+20h], 0
0x14000f9ae  mov     rbx, [rsp+48h+arg_0]
0x14000f9b3  xor     eax, eax
0x14000f9b5  add     rsp, 40h
0x14000f9b9  pop     rdi
0x14000f9ba  retn
```

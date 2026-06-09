# BfValidateContainerRootId

- ea: `0x14001e5c8`
- end: `0x14001e6f5`
- name: `BfValidateContainerRootId`
- size: `301`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010898`
- `0x14001d2c0`
- `0x14001d974`
- `0x14001ea74`
- `0x14001f40c`
- `0x14001fb68`

## callees

- `0x140001348`
- `0x140003304`
- `0x14001e5c8`

## pseudocode

```c
__int64 __fastcall BfValidateContainerRootId(unsigned __int16 *a1, int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // r9d
  char v6; // [rsp+30h] [rbp-18h]
  int v7; // [rsp+38h] [rbp-10h]

  v2 = *a1;
  if ( v2 != a2 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741811;
    v5 = 16;
    v6 = -99;
    goto LABEL_15;
  }
  a2 = a1[2];
  if ( (unsigned int)(a2 + 6) >= 6 )
  {
    if ( v2 == a2 + 6 )
    {
      v3 = 0;
      if ( a1[1] <= (unsigned __int16)a2 )
        return v3;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v5 = 19;
        v6 = -77;
        goto LABEL_15;
      }
      return (unsigned int)-1073741811;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741811;
    v5 = 18;
    v6 = -84;
LABEL_15:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      6,
      v5,
      (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
      v6);
    return (unsigned int)-1073741811;
  }
  v3 = -1073741675;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = -1073741675;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      6,
      17,
      (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
      166,
      v7);
  }
  return v3;
}

```

## disassembly

```asm
0x14001e5c8  push    rbx
0x14001e5ca  sub     rsp, 40h
0x14001e5ce  movzx   eax, word ptr [rcx]
0x14001e5d1  cmp     eax, edx
0x14001e5d3  jnz     loc_14001E65D
0x14001e5d9  movzx   edx, word ptr [rcx+4]
0x14001e5dd  mov     r8d, 6
0x14001e5e3  lea     r9d, [rdx+6]
0x14001e5e7  cmp     r9d, r8d
0x14001e5ea  jb      short loc_14001E60A
0x14001e5ec  cmp     eax, r9d
0x14001e5ef  jnz     loc_14001E688
0x14001e5f5  xor     ebx, ebx
0x14001e5f7  cmp     [rcx+2], dx
0x14001e5fb  ja      loc_14001E6A8
0x14001e601  mov     eax, ebx
0x14001e603  add     rsp, 40h
0x14001e607  pop     rbx
0x14001e608  retn
0x14001e60a  mov     ebx, 0C0000095h
0x14001e60f  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e616  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e61d  jz      short loc_14001E601
0x14001e61f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e626  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001e62d  mov     [rsp+48h+var_10], ebx
0x14001e631  mov     r9d, 11h
0x14001e637  mov     dword ptr [rsp+48h+var_18], 3A6h
0x14001e63f  mov     dl, 2
0x14001e641  mov     [rsp+48h+var_20], rax
0x14001e646  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x14001e64d  mov     rcx, [rcx+40h]
0x14001e651  mov     [rsp+48h+var_28], rax
0x14001e656  call    WPP_RECORDER_SF_sDd
0x14001e65b  jmp     short loc_14001E601
0x14001e65d  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e664  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e66b  jnz     short loc_14001E674
0x14001e66d  mov     ebx, 0C000000Dh
0x14001e672  jmp     short loc_14001E601
0x14001e674  mov     r9d, 10h
0x14001e67a  mov     dword ptr [rsp+48h+var_18], 39Dh
0x14001e682  lea     r8d, [r9-0Ah]
0x14001e686  jmp     short loc_14001E6C6
0x14001e688  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e68f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e696  jz      short loc_14001E66D
0x14001e698  mov     r9d, 12h
0x14001e69e  mov     dword ptr [rsp+48h+var_18], 3ACh
0x14001e6a6  jmp     short loc_14001E6C6
0x14001e6a8  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e6af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e6b6  jz      short loc_14001E66D
0x14001e6b8  mov     r9d, 13h
0x14001e6be  mov     dword ptr [rsp+48h+var_18], 3B3h
0x14001e6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e6cd  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001e6d4  mov     [rsp+48h+var_20], rax
0x14001e6d9  mov     dl, 2
0x14001e6db  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x14001e6e2  mov     [rsp+48h+var_28], rax
0x14001e6e7  mov     rcx, [rcx+40h]
0x14001e6eb  call    WPP_RECORDER_SF_sD
0x14001e6f0  jmp     loc_14001E66D
```

# BfpValidateVirtualizationRoot

- ea: `0x14001fb68`
- end: `0x14001fce6`
- name: `BfpValidateVirtualizationRoot`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140010384`
- `0x140010d64`
- `0x14001f71c`

## callees

- `0x140001348`
- `0x140003304`
- `0x14001e5c8`
- `0x14001fb68`

## pseudocode

```c
__int64 __fastcall BfpValidateVirtualizationRoot(unsigned __int64 a1, unsigned int *a2, unsigned int a3, _QWORD *a4)
{
  __int64 v4; // rax
  int v6; // r9d
  unsigned int v7; // edx
  __int64 v8; // rdi
  unsigned int v9; // ebx
  int v11; // r9d
  char v12; // [rsp+30h] [rbp-18h]
  int v13; // [rsp+38h] [rbp-10h]

  v4 = *a2;
  *a4 = 0;
  v6 = *((unsigned __int16 *)a2 + 2);
  v7 = v4 + v6;
  if ( (int)v4 + v6 < (unsigned int)v4 )
  {
    v9 = -1073741675;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v9;
    v13 = -1073741675;
    v11 = 38;
    v12 = 65;
    goto LABEL_9;
  }
  if ( v7 <= a3 )
  {
    v8 = a1 + v4;
    if ( a1 + v4 < a1 )
    {
      v9 = -1073741675;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v9;
      v13 = -1073741675;
      v11 = 40;
      v12 = 86;
    }
    else
    {
      v9 = BfValidateContainerRootId((unsigned __int16 *)(a1 + v4), v6);
      if ( (v9 & 0x80000000) == 0 )
      {
        *a4 = v8;
        return 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v9;
      v13 = v9;
      v11 = 41;
      v12 = 96;
    }
LABEL_9:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      6,
      v11,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v12,
      v13);
    return v9;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      6,
      39,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      71);
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x14001fb68  mov     [rsp+arg_0], rbx
0x14001fb6d  mov     [rsp+arg_8], rsi
0x14001fb72  push    rdi
0x14001fb73  sub     rsp, 40h
0x14001fb77  mov     eax, [rdx]
0x14001fb79  mov     rsi, r9
0x14001fb7c  mov     qword ptr [r9], 0
0x14001fb83  movzx   r9d, word ptr [rdx+4]
0x14001fb88  lea     edx, [rax+r9]
0x14001fb8c  cmp     edx, eax
0x14001fb8e  jb      short loc_14001FBD3
0x14001fb90  cmp     edx, r8d
0x14001fb93  ja      loc_14001FC45
0x14001fb99  lea     rdi, [rcx+rax]
0x14001fb9d  cmp     rdi, rcx
0x14001fba0  jb      loc_14001FC9B
0x14001fba6  mov     edx, r9d
0x14001fba9  mov     rcx, rdi
0x14001fbac  call    BfValidateContainerRootId
0x14001fbb1  mov     ebx, eax
0x14001fbb3  test    eax, eax
0x14001fbb5  js      loc_14001FCCD
0x14001fbbb  mov     [rsi], rdi
0x14001fbbe  xor     ebx, ebx
0x14001fbc0  mov     rsi, [rsp+48h+arg_8]
0x14001fbc5  mov     eax, ebx
0x14001fbc7  mov     rbx, [rsp+48h+arg_0]
0x14001fbcc  add     rsp, 40h
0x14001fbd0  pop     rdi
0x14001fbd1  retn
0x14001fbd3  mov     ecx, 0C0000095h
0x14001fbd8  mov     ebx, ecx
0x14001fbda  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fbe1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fbe8  jz      short loc_14001FBC0
0x14001fbea  mov     [rsp+48h+var_10], ecx
0x14001fbee  mov     r9d, 26h ; '&'
0x14001fbf4  mov     dword ptr [rsp+48h+var_18], 741h
0x14001fbfc  jmp     short loc_14001FC10
0x14001fbfe  mov     [rsp+48h+var_10], ebx
0x14001fc02  mov     r9d, 29h ; ')'
0x14001fc08  mov     dword ptr [rsp+48h+var_18], 760h
0x14001fc10  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc17  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001fc1e  mov     [rsp+48h+var_20], rax
0x14001fc23  mov     r8d, 6
0x14001fc29  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001fc30  mov     dl, 2
0x14001fc32  mov     [rsp+48h+var_28], rax
0x14001fc37  mov     rcx, [rcx+40h]
0x14001fc3b  call    WPP_RECORDER_SF_sDd
0x14001fc40  jmp     loc_14001FBC0
0x14001fc45  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fc4c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fc53  jz      short loc_14001FC91
0x14001fc55  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc5c  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001fc63  mov     r9d, 27h ; '''
0x14001fc69  mov     dword ptr [rsp+48h+var_18], 747h
0x14001fc71  mov     [rsp+48h+var_20], rax
0x14001fc76  mov     dl, 2
0x14001fc78  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001fc7f  mov     rcx, [rcx+40h]
0x14001fc83  lea     r8d, [r9-21h]
0x14001fc87  mov     [rsp+48h+var_28], rax
0x14001fc8c  call    WPP_RECORDER_SF_sD
0x14001fc91  mov     ebx, 0C000000Dh
0x14001fc96  jmp     loc_14001FBC0
0x14001fc9b  mov     ecx, 0C0000095h
0x14001fca0  mov     ebx, ecx
0x14001fca2  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fca9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fcb0  jz      loc_14001FBC0
0x14001fcb6  mov     [rsp+48h+var_10], ecx
0x14001fcba  mov     r9d, 28h ; '('
0x14001fcc0  mov     dword ptr [rsp+48h+var_18], 756h
0x14001fcc8  jmp     loc_14001FC10
0x14001fccd  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fcd4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fcdb  jz      loc_14001FBC0
0x14001fce1  jmp     loc_14001FBFE
```

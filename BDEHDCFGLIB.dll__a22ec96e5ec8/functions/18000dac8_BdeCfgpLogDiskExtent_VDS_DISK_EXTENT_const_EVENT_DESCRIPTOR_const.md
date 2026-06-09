# BdeCfgpLogDiskExtent(_VDS_DISK_EXTENT const *,_EVENT_DESCRIPTOR const *)

- ea: `0x18000dac8`
- end: `0x18000dbab`
- name: `?BdeCfgpLogDiskExtent@@YAJPEBU_VDS_DISK_EXTENT@@PEBU_EVENT_DESCRIPTOR@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(const struct _VDS_DISK_EXTENT *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e2d0`
- `0x18000e750`

## callees

- `0x18000dac8`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000db6c`
- `ADVAPI32!EventWrite` at `0x18000db6c`

## pseudocode

```c
__int64 __fastcall BdeCfgpLogDiskExtent(const struct _VDS_DISK_EXTENT *a1, const struct _EVENT_DESCRIPTOR *a2)
{
  int v2; // ebx
  signed int v3; // eax
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-68h] BYREF
  VDS_DISK_EXTENT_TYPE *p_type; // [rsp+40h] [rbp-58h]
  __int64 v7; // [rsp+48h] [rbp-50h]
  ULONGLONG *p_ullOffset; // [rsp+50h] [rbp-48h]
  __int64 v9; // [rsp+58h] [rbp-40h]
  ULONGLONG *p_ullSize; // [rsp+60h] [rbp-38h]
  __int64 v11; // [rsp+68h] [rbp-30h]
  VDS_OBJECT_ID *p_volumeId; // [rsp+70h] [rbp-28h]
  __int64 v13; // [rsp+78h] [rbp-20h]

  if ( a1 && a2 )
  {
    v2 = 0;
    if ( !g_EventRegistrationHandle )
      v2 = -1063256042;
    if ( v2 >= 0 )
    {
      v5.Ptr = (ULONGLONG)a1;
      *(_QWORD *)&v5.Size = 16;
      p_type = &a1->type;
      v7 = 4;
      p_ullOffset = &a1->ullOffset;
      v9 = 8;
      p_ullSize = &a1->ullSize;
      v11 = 8;
      p_volumeId = &a1->volumeId;
      v13 = 16;
      v3 = EventWrite(g_EventRegistrationHandle, a2, 5u, &v5);
      if ( v3 )
      {
        if ( v3 > 0 )
          return (unsigned __int16)v3 | 0x80070000;
        else
          return (unsigned int)v3;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000dac8  mov     r11, rsp
0x18000dacb  push    rbx
0x18000dacc  sub     rsp, 90h
0x18000dad3  mov     rax, cs:__security_cookie
0x18000dada  xor     rax, rsp
0x18000dadd  mov     [rsp+98h+var_18], rax
0x18000dae5  test    rcx, rcx
0x18000dae8  jz      loc_18000DB87
0x18000daee  test    rdx, rdx
0x18000daf1  jz      loc_18000DB87
0x18000daf7  xor     ebx, ebx
0x18000daf9  mov     eax, 0C0A00016h
0x18000dafe  mov     r10, cs:?g_EventRegistrationHandle@@3_KA; unsigned __int64 g_EventRegistrationHandle
0x18000db05  test    r10, r10
0x18000db08  cmovz   ebx, eax
0x18000db0b  mov     [rsp+98h+var_78], ebx
0x18000db0f  test    ebx, ebx
0x18000db11  js      short loc_18000DB90
0x18000db13  mov     [r11-68h], rcx
0x18000db17  mov     qword ptr [r11-60h], 10h
0x18000db1f  lea     rax, [rcx+10h]
0x18000db23  mov     [r11-58h], rax
0x18000db27  mov     qword ptr [r11-50h], 4
0x18000db2f  lea     rax, [rcx+18h]
0x18000db33  mov     [r11-48h], rax
0x18000db37  mov     qword ptr [r11-40h], 8
0x18000db3f  lea     rax, [rcx+20h]
0x18000db43  mov     [r11-38h], rax
0x18000db47  mov     qword ptr [r11-30h], 8
0x18000db4f  lea     rax, [rcx+28h]
0x18000db53  mov     [r11-28h], rax
0x18000db57  mov     qword ptr [r11-20h], 10h
0x18000db5f  lea     r9, [r11-68h]; UserData
0x18000db63  mov     r8d, 5; UserDataCount
0x18000db69  mov     rcx, r10; RegHandle
0x18000db6c  call    cs:__imp_EventWrite
0x18000db72  test    eax, eax
0x18000db74  jz      short loc_18000DB90
0x18000db76  jg      short loc_18000DB7C
0x18000db78  mov     ebx, eax
0x18000db7a  jmp     short loc_18000DB8C
0x18000db7c  movzx   ebx, ax
0x18000db7f  or      ebx, 80070000h
0x18000db85  jmp     short loc_18000DB8C
0x18000db87  mov     ebx, 80070057h
0x18000db8c  mov     [rsp+98h+var_78], ebx
0x18000db90  mov     eax, ebx
0x18000db92  mov     rcx, [rsp+98h+var_18]
0x18000db9a  xor     rcx, rsp; StackCookie
0x18000db9d  call    __security_check_cookie
0x18000dba2  add     rsp, 90h
0x18000dba9  pop     rbx
0x18000dbaa  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```

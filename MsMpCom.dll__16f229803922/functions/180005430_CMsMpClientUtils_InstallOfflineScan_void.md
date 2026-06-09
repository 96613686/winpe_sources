# CMsMpClientUtils::InstallOfflineScan(void)

- ea: `0x180005430`
- end: `0x18000547b`
- name: `?InstallOfflineScan@CMsMpClientUtils@@UEAAJXZ`
- size: `75`
- prototype: `__int64 __fastcall(CMsMpClientUtils *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180005430`
- `0x180005b0c`

## import_xrefs

- `mpclient!MpOfflineScanInstall` at `0x180005474`

## pseudocode

```c
__int64 __fastcall CMsMpClientUtils::InstallOfflineScan(CMsMpClientUtils *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 25);
  return MpOfflineScanInstall(*((_QWORD *)this + 1), 0);
}

```

## disassembly

```asm
0x180005430  push    rbx
0x180005432  sub     rsp, 30h
0x180005436  mov     rbx, rcx
0x180005439  mov     rcx, cs:WPP_GLOBAL_Control
0x180005440  lea     rax, WPP_GLOBAL_Control
0x180005447  cmp     rcx, rax
0x18000544a  jz      short loc_180005469
0x18000544c  test    byte ptr [rcx+1Ch], 8
0x180005450  jz      short loc_180005469
0x180005452  mov     rcx, [rcx+10h]
0x180005456  lea     rax, [rbx-40h]
0x18000545a  mov     edx, 19h
0x18000545f  mov     [rsp+38h+var_18], rax
0x180005464  call    WPP_SF_sq
0x180005469  mov     rcx, [rbx+8]
0x18000546d  xor     edx, edx
0x18000546f  add     rsp, 30h
0x180005473  pop     rbx
0x180005474  jmp     cs:__imp_MpOfflineScanInstall
```

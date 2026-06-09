# CMsMpClientUtils::ThreatHistoryRemoveAll(void)

- ea: `0x1800057a0`
- end: `0x1800057ee`
- name: `?ThreatHistoryRemoveAll@CMsMpClientUtils@@UEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(CMsMpClientUtils *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800057a0`
- `0x180005b0c`

## import_xrefs

- `mpclient!MpThreatHistoryRequest` at `0x1800057e7`

## pseudocode

```c
__int64 __fastcall CMsMpClientUtils::ThreatHistoryRemoveAll(CMsMpClientUtils *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 15);
  return MpThreatHistoryRequest(*((_QWORD *)this + 1), 1);
}

```

## disassembly

```asm
0x1800057a0  push    rbx
0x1800057a2  sub     rsp, 30h
0x1800057a6  mov     rbx, rcx
0x1800057a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057b0  lea     rax, WPP_GLOBAL_Control
0x1800057b7  cmp     rcx, rax
0x1800057ba  jz      short loc_1800057D9
0x1800057bc  test    byte ptr [rcx+1Ch], 8
0x1800057c0  jz      short loc_1800057D9
0x1800057c2  mov     rcx, [rcx+10h]
0x1800057c6  lea     rax, [rbx-40h]
0x1800057ca  mov     edx, 0Fh
0x1800057cf  mov     [rsp+38h+var_18], rax
0x1800057d4  call    WPP_SF_sq
0x1800057d9  mov     rcx, [rbx+8]
0x1800057dd  mov     edx, 1
0x1800057e2  add     rsp, 30h
0x1800057e6  pop     rbx
0x1800057e7  jmp     cs:__imp_MpThreatHistoryRequest
```

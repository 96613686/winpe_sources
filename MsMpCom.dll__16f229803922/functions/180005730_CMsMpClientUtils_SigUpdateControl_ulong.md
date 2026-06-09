# CMsMpClientUtils::SigUpdateControl(ulong)

- ea: `0x180005730`
- end: `0x180005791`
- name: `?SigUpdateControl@CMsMpClientUtils@@UEAAJK@Z`
- size: `97`
- prototype: `__int64 __fastcall(CMsMpClientUtils *this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180005730`
- `0x180005b0c`

## import_xrefs

- `mpclient!MpUpdateControl` at `0x180005780`
- `mpclient!MpUpdateControl` at `0x180005780`

## pseudocode

```c
__int64 __fastcall CMsMpClientUtils::SigUpdateControl(CMsMpClientUtils *this, int a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 20);
  if ( a2 )
    return 2147942487LL;
  else
    return MpUpdateControl(*((_QWORD *)this + 1), 0);
}

```

## disassembly

```asm
0x180005730  mov     [rsp+arg_0], rbx
0x180005735  push    rdi
0x180005736  sub     rsp, 30h
0x18000573a  mov     edi, edx
0x18000573c  mov     rbx, rcx
0x18000573f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005746  lea     rax, WPP_GLOBAL_Control
0x18000574d  cmp     rcx, rax
0x180005750  jz      short loc_18000576F
0x180005752  test    byte ptr [rcx+1Ch], 8
0x180005756  jz      short loc_18000576F
0x180005758  mov     rcx, [rcx+10h]
0x18000575c  lea     rax, [rbx-40h]
0x180005760  mov     edx, 14h
0x180005765  mov     [rsp+38h+var_18], rax
0x18000576a  call    WPP_SF_sq
0x18000576f  test    edi, edi
0x180005771  jz      short loc_18000577A
0x180005773  mov     eax, 80070057h
0x180005778  jmp     short loc_180005786
0x18000577a  mov     rcx, [rbx+8]
0x18000577e  xor     edx, edx
0x180005780  call    cs:__imp_MpUpdateControl
0x180005786  mov     rbx, [rsp+38h+arg_0]
0x18000578b  add     rsp, 30h
0x18000578f  pop     rdi
0x180005790  retn
```

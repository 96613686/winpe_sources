# CommonUtil::UtilGetWindowsPath

- ea: `0x1800070b8`
- end: `0x180007141`
- name: `CommonUtil::UtilGetWindowsPath`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007304`

## callees

- `0x180006eb0`
- `0x1800070b8`
- `0x180007a44`
- `0x180007d9c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007129`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007129`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetWindowsPath(
        __int64 (__fastcall *a1)(_WORD *, _QWORD),
        CommonUtil *a2,
        __int64 a3)
{
  int WindowsPath; // edi
  const unsigned __int16 *v6; // r8
  unsigned __int16 **v7; // rcx
  __int64 v8; // r9
  unsigned __int16 **v9; // rbx
  int v10; // eax
  unsigned __int16 **v12; // [rsp+20h] [rbp-18h] BYREF

  v12 = 0;
  WindowsPath = CommonUtil::HrGetWindowsPath(a1, &v12);
  if ( WindowsPath >= 0 )
  {
    if ( a3 )
    {
      v8 = a3;
      v9 = v12;
      v10 = CommonUtil::NewSprintfW(a2, (unsigned __int16 **)L"%ws\\%ws", (const unsigned __int16 *)v12, v8);
    }
    else
    {
      v9 = v12;
      v10 = CommonUtil::HrDuplicateStringW((void **)a2, v12, v6);
    }
    WindowsPath = v10;
    if ( v9 )
    {
      v7 = v9;
LABEL_9:
      operator delete[](v7);
    }
  }
  else
  {
    v7 = v12;
    if ( v12 )
      goto LABEL_9;
  }
  return (unsigned int)WindowsPath;
}

```

## disassembly

```asm
0x1800070b8  mov     rax, rsp
0x1800070bb  mov     [rax+8], rbx
0x1800070bf  mov     [rax+10h], rsi
0x1800070c3  push    rdi
0x1800070c4  sub     rsp, 30h
0x1800070c8  mov     rsi, rdx
0x1800070cb  mov     qword ptr [rax-18h], 0
0x1800070d3  lea     rdx, [rax-18h]
0x1800070d7  mov     rbx, r8
0x1800070da  call    CommonUtil__HrGetWindowsPath
0x1800070df  mov     edi, eax
0x1800070e1  test    eax, eax
0x1800070e3  jns     short loc_1800070F1
0x1800070e5  mov     rcx, [rsp+38h+var_18]
0x1800070ea  test    rcx, rcx
0x1800070ed  jz      short loc_18000712F
0x1800070ef  jmp     short loc_180007129
0x1800070f1  mov     rcx, rsi; this
0x1800070f4  test    rbx, rbx
0x1800070f7  jz      short loc_180007112
0x1800070f9  mov     r9, rbx
0x1800070fc  lea     rdx, aWsWs; "%ws\\%ws"
0x180007103  mov     rbx, [rsp+38h+var_18]
0x180007108  mov     r8, rbx; unsigned __int16 *
0x18000710b  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180007110  jmp     short loc_18000711F
0x180007112  mov     rbx, [rsp+38h+var_18]
0x180007117  mov     rdx, rbx; unsigned __int16 **
0x18000711a  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x18000711f  mov     edi, eax
0x180007121  test    rbx, rbx
0x180007124  jz      short loc_18000712F
0x180007126  mov     rcx, rbx
0x180007129  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000712f  mov     rbx, [rsp+38h+arg_0]
0x180007134  mov     eax, edi
0x180007136  mov     rsi, [rsp+38h+arg_8]
0x18000713b  add     rsp, 30h
0x18000713f  pop     rdi
0x180007140  retn
```

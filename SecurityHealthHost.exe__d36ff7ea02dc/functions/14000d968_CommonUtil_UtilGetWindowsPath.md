# CommonUtil::UtilGetWindowsPath

- ea: `0x14000d968`
- end: `0x14000d9df`
- name: `CommonUtil::UtilGetWindowsPath`
- size: `119`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(void *, _QWORD), CommonUtil *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140005fdc`

## callees

- `0x140001614`
- `0x14000d778`
- `0x14000d968`
- `0x14000de38`

## string_xrefs

- `0x14000d9aa`: `MsMpLics.dll`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetWindowsPath(__int64 (__fastcall *a1)(void *, _QWORD), CommonUtil *a2)
{
  int WindowsPath; // ebx
  unsigned __int16 *v5; // rbx
  unsigned int v6; // edi
  unsigned __int16 *v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  WindowsPath = CommonUtil::HrGetWindowsPath(a1, &v7);
  if ( WindowsPath >= 0 )
  {
    v5 = v7;
    v6 = CommonUtil::NewSprintfW(a2, (unsigned __int16 **)L"%ws\\%ws", v7, (char *)L"MsMpLics.dll");
    if ( v5 )
      operator delete(v5);
    return v6;
  }
  else
  {
    if ( v7 )
      operator delete(v7);
    return (unsigned int)WindowsPath;
  }
}

```

## disassembly

```asm
0x14000d968  mov     rax, rsp
0x14000d96b  mov     [rax+8], rbx
0x14000d96f  mov     [rax+18h], r8
0x14000d973  push    rdi
0x14000d974  sub     rsp, 20h
0x14000d978  mov     rdi, rdx
0x14000d97b  mov     qword ptr [rax+18h], 0
0x14000d983  lea     rdx, [rax+18h]
0x14000d987  call    CommonUtil__HrGetWindowsPath
0x14000d98c  mov     ebx, eax
0x14000d98e  test    eax, eax
0x14000d990  jns     short loc_14000D9A5
0x14000d992  mov     rcx, [rsp+28h+arg_10]; void *
0x14000d997  test    rcx, rcx
0x14000d99a  jz      short loc_14000D9A1
0x14000d99c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d9a1  mov     eax, ebx
0x14000d9a3  jmp     short loc_14000D9D4
0x14000d9a5  mov     rbx, [rsp+28h+arg_10]
0x14000d9aa  lea     r9, aMsmplicsDll; "MsMpLics.dll"
0x14000d9b1  mov     r8, rbx; unsigned __int16 *
0x14000d9b4  lea     rdx, aWsWs; "%ws\\%ws"
0x14000d9bb  mov     rcx, rdi; this
0x14000d9be  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x14000d9c3  mov     edi, eax
0x14000d9c5  test    rbx, rbx
0x14000d9c8  jz      short loc_14000D9D2
0x14000d9ca  mov     rcx, rbx; void *
0x14000d9cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d9d2  mov     eax, edi
0x14000d9d4  mov     rbx, [rsp+28h+arg_0]
0x14000d9d9  add     rsp, 20h
0x14000d9dd  pop     rdi
0x14000d9de  retn
```

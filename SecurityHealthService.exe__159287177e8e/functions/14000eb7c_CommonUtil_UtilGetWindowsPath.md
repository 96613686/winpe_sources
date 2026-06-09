# CommonUtil::UtilGetWindowsPath

- ea: `0x14000eb7c`
- end: `0x14000ec04`
- name: `CommonUtil::UtilGetWindowsPath`
- size: `136`
- prototype: `__int64 __fastcall(__int64, CommonUtil *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003e58`
- `0x140004e84`
- `0x140007538`
- `0x14000ed24`

## callees

- `0x1400015f4`
- `0x14000e800`
- `0x14000eb7c`
- `0x14000f3ac`
- `0x1400100bc`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetWindowsPath(__int64 a1, CommonUtil *a2, __int64 a3)
{
  unsigned __int64 v5; // rdx
  int WindowsPath; // edi
  const unsigned __int16 *v7; // r8
  unsigned __int16 **v8; // rcx
  __int64 v9; // r9
  unsigned __int16 **v10; // rbx
  int v11; // eax
  unsigned __int16 **v13; // [rsp+20h] [rbp-18h] BYREF

  v13 = 0;
  WindowsPath = CommonUtil::HrGetWindowsPath(a1, &v13);
  if ( WindowsPath >= 0 )
  {
    if ( a3 )
    {
      v9 = a3;
      v10 = v13;
      v11 = CommonUtil::NewSprintfW(a2, (unsigned __int16 **)L"%ws\\%ws", (const unsigned __int16 *)v13, v9);
    }
    else
    {
      v10 = v13;
      v11 = CommonUtil::HrDuplicateStringW(a2, v13, v7);
    }
    WindowsPath = v11;
    if ( v10 )
    {
      v8 = v10;
LABEL_9:
      operator delete(v8, v5);
    }
  }
  else
  {
    v8 = v13;
    if ( v13 )
      goto LABEL_9;
  }
  return (unsigned int)WindowsPath;
}

```

## disassembly

```asm
0x14000eb7c  mov     rax, rsp
0x14000eb7f  mov     [rax+8], rbx
0x14000eb83  mov     [rax+10h], rsi
0x14000eb87  push    rdi
0x14000eb88  sub     rsp, 30h
0x14000eb8c  mov     rsi, rdx
0x14000eb8f  mov     qword ptr [rax-18h], 0
0x14000eb97  lea     rdx, [rax-18h]
0x14000eb9b  mov     rbx, r8
0x14000eb9e  call    CommonUtil__HrGetWindowsPath
0x14000eba3  mov     edi, eax
0x14000eba5  test    eax, eax
0x14000eba7  jns     short loc_14000EBB5
0x14000eba9  mov     rcx, [rsp+38h+var_18]
0x14000ebae  test    rcx, rcx
0x14000ebb1  jz      short loc_14000EBF2
0x14000ebb3  jmp     short loc_14000EBED
0x14000ebb5  mov     rcx, rsi; this
0x14000ebb8  test    rbx, rbx
0x14000ebbb  jz      short loc_14000EBD6
0x14000ebbd  mov     r9, rbx
0x14000ebc0  lea     rdx, aWsWs; "%ws\\%ws"
0x14000ebc7  mov     rbx, [rsp+38h+var_18]
0x14000ebcc  mov     r8, rbx; unsigned __int16 *
0x14000ebcf  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x14000ebd4  jmp     short loc_14000EBE3
0x14000ebd6  mov     rbx, [rsp+38h+var_18]
0x14000ebdb  mov     rdx, rbx; unsigned __int16 **
0x14000ebde  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x14000ebe3  mov     edi, eax
0x14000ebe5  test    rbx, rbx
0x14000ebe8  jz      short loc_14000EBF2
0x14000ebea  mov     rcx, rbx; void *
0x14000ebed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ebf2  mov     rbx, [rsp+38h+arg_0]
0x14000ebf7  mov     eax, edi
0x14000ebf9  mov     rsi, [rsp+38h+arg_8]
0x14000ebfe  add     rsp, 30h
0x14000ec02  pop     rdi
0x14000ec03  retn
```

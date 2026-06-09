# CommonUtil::UtilWriteFile(void *,unsigned __int64,void const *)

- ea: `0x1400047e0`
- end: `0x1400048ba`
- name: `?UtilWriteFile@CommonUtil@@YAJPEAX_KPEBX@Z`
- size: `218`
- prototype: `__int64 __fastcall(HANDLE hFile, void *, unsigned __int64, const void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002380c`

## callees

- `0x1400047e0`
- `0x14000493c`
- `0x140005c20`
- `0x14001da70`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140004848`
- `KERNEL32!WriteFile` at `0x140004848`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilWriteFile(HANDLE hFile, void *a2, char *a3, const void *a4)
{
  int LastFailure; // ebx
  DWORD v6; // edi
  HANDLE v7; // rbp
  DWORD i; // r8d
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-28h] BYREF

  LastFailure = 0;
  v6 = (unsigned int)a2;
  v7 = hFile;
  if ( (void *)(unsigned int)a2 != a2 )
    return 2147942487LL;
  for ( i = (unsigned int)a2; ; i = v6 )
  {
    NumberOfBytesWritten = 0;
    if ( !WriteFile(hFile, a3, i, &NumberOfBytesWritten, 0) )
    {
      LastFailure = HrGetLastFailure();
      goto LABEL_10;
    }
    if ( NumberOfBytesWritten == v6 )
      goto LABEL_10;
    if ( !NumberOfBytesWritten || NumberOfBytesWritten > v6 )
      break;
    v6 -= NumberOfBytesWritten;
    hFile = v7;
    a3 += NumberOfBytesWritten;
  }
  LastFailure = -2147418113;
LABEL_10:
  if ( LastFailure >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_bed851edf8673fd54b380593fb017a56_Traceguids,
      (unsigned int)LastFailure);
  return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x1400047e0  mov     [rsp+arg_18], rbx
0x1400047e5  push    rbp
0x1400047e6  push    rsi
0x1400047e7  push    rdi
0x1400047e8  sub     rsp, 40h
0x1400047ec  mov     rax, cs:__security_cookie
0x1400047f3  xor     rax, rsp
0x1400047f6  mov     [rsp+58h+var_20], rax
0x1400047fb  xor     ebx, ebx
0x1400047fd  mov     eax, edx
0x1400047ff  mov     rsi, r8
0x140004802  mov     rdi, rdx
0x140004805  mov     rbp, rcx
0x140004808  cmp     rax, rdx
0x14000480b  jz      short loc_140004817
0x14000480d  mov     eax, 80070057h
0x140004812  jmp     loc_1400048A0
0x140004817  mov     r8d, edx
0x14000481a  jmp     short loc_140004837
0x14000481c  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x140004820  cmp     eax, edi
0x140004822  jz      short loc_140004859
0x140004824  test    eax, eax
0x140004826  jz      short loc_140004897
0x140004828  cmp     eax, edi
0x14000482a  ja      short loc_140004897
0x14000482c  sub     edi, eax
0x14000482e  mov     rcx, rbp; hFile
0x140004831  add     rsi, rax
0x140004834  mov     r8d, edi; nNumberOfBytesToWrite
0x140004837  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000483c  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x140004841  mov     rdx, rsi; lpBuffer
0x140004844  mov     [rsp+58h+NumberOfBytesWritten], ebx
0x140004848  call    cs:__imp_WriteFile
0x14000484e  test    eax, eax
0x140004850  jnz     short loc_14000481C
0x140004852  call    HrGetLastFailure
0x140004857  mov     ebx, eax
0x140004859  mov     ecx, ebx
0x14000485b  shr     ecx, 1Fh
0x14000485e  test    cl, cl
0x140004860  jz      short loc_14000489E
0x140004862  mov     rcx, cs:WPP_GLOBAL_Control
0x140004869  lea     rax, WPP_GLOBAL_Control
0x140004870  cmp     rcx, rax
0x140004873  jz      short loc_140004893
0x140004875  test    byte ptr [rcx+1Ch], 1
0x140004879  jz      short loc_140004893
0x14000487b  mov     rcx, [rcx+10h]
0x14000487f  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x140004886  mov     edx, 17h
0x14000488b  mov     r9d, ebx
0x14000488e  call    WPP_SF_d
0x140004893  mov     eax, ebx
0x140004895  jmp     short loc_1400048A0
0x140004897  mov     ebx, 8000FFFFh
0x14000489c  jmp     short loc_140004859
0x14000489e  xor     eax, eax
0x1400048a0  mov     rcx, [rsp+58h+var_20]
0x1400048a5  xor     rcx, rsp; StackCookie
0x1400048a8  call    __security_check_cookie
0x1400048ad  mov     rbx, [rsp+58h+arg_18]
0x1400048b2  add     rsp, 40h
0x1400048b6  pop     rdi
0x1400048b7  pop     rsi
0x1400048b8  pop     rbp
0x1400048b9  retn
```

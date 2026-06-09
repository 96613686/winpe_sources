# CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x140013110`
- end: `0x1400131e2`
- name: `?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z`
- size: `210`
- prototype: `int(CommonUtil *__hidden this, void **, const wchar_t *, unsigned int, unsigned int, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d93c`
- `0x1400814f4`
- `0x1400f4ae8`
- `0x1400f4ea8`

## callees

- `0x140013110`
- `0x140017738`
- `0x140085d94`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14001315b`
- `KERNEL32!CreateFileW` at `0x14001315b`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilCreateFile(
        CommonUtil *this,
        const WCHAR *a2,
        const wchar_t *a3,
        DWORD a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        struct _SECURITY_ATTRIBUTES *hTemplateFile)
{
  int v8; // edi
  HANDLE FileW; // rax
  unsigned int LastFailure; // ebx
  __int64 v13; // rcx
  int v14; // edx

  v8 = (int)a2;
  *(_QWORD *)this = -1;
  FileW = CreateFileW(
            a2,
            (DWORD)a3,
            a4,
            lpSecurityAttributes,
            dwCreationDisposition,
            dwFlagsAndAttributes,
            hTemplateFile);
  *(_QWORD *)this = FileW;
  if ( FileW != (HANDLE)-1LL )
    return 0;
  LastFailure = HrGetLastFailure();
  if ( LastFailure + 2147024894 <= 1 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      return LastFailure;
    v14 = 16;
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      return LastFailure;
    v14 = 17;
  }
  WPP_SF_Sd(*(_QWORD *)(v13 + 16), v14, (unsigned int)WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids, v8, LastFailure);
  return LastFailure;
}

```

## disassembly

```asm
0x140013110  mov     [rsp+arg_0], rbx
0x140013115  push    rdi
0x140013116  sub     rsp, 40h
0x14001311a  mov     rax, [rsp+48h+arg_38]
0x140013122  mov     r10d, r9d
0x140013125  mov     r9, [rsp+48h+lpSecurityAttributes]; lpSecurityAttributes
0x14001312d  mov     r11d, r8d
0x140013130  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x140013135  mov     rdi, rdx
0x140013138  mov     eax, [rsp+48h+arg_28]
0x14001313c  mov     rbx, rcx
0x14001313f  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x140013143  mov     r8d, r10d; dwShareMode
0x140013146  mov     eax, [rsp+48h+arg_20]
0x14001314a  mov     edx, r11d; dwDesiredAccess
0x14001314d  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140013154  mov     rcx, rdi; lpFileName
0x140013157  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x14001315b  call    cs:__imp_CreateFileW
0x140013161  mov     [rbx], rax
0x140013164  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140013168  jz      short loc_14001316E
0x14001316a  xor     eax, eax
0x14001316c  jmp     short loc_1400131D7
0x14001316e  call    HrGetLastFailure
0x140013173  mov     ebx, eax
0x140013175  lea     ecx, [rax+7FF8FFFEh]
0x14001317b  cmp     ecx, 1
0x14001317e  jbe     short loc_1400131A0
0x140013180  mov     rcx, cs:WPP_GLOBAL_Control
0x140013187  lea     rax, WPP_GLOBAL_Control
0x14001318e  cmp     rcx, rax
0x140013191  jz      short loc_1400131D5
0x140013193  test    byte ptr [rcx+1Ch], 1
0x140013197  jz      short loc_1400131D5
0x140013199  mov     edx, 11h
0x14001319e  jmp     short loc_1400131BE
0x1400131a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131a7  lea     rax, WPP_GLOBAL_Control
0x1400131ae  cmp     rcx, rax
0x1400131b1  jz      short loc_1400131D5
0x1400131b3  test    byte ptr [rcx+1Ch], 4
0x1400131b7  jz      short loc_1400131D5
0x1400131b9  mov     edx, 10h
0x1400131be  mov     rcx, [rcx+10h]
0x1400131c2  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x1400131c9  mov     r9, rdi
0x1400131cc  mov     [rsp+48h+dwCreationDisposition], ebx
0x1400131d0  call    WPP_SF_Sd
0x1400131d5  mov     eax, ebx
0x1400131d7  mov     rbx, [rsp+48h+arg_0]
0x1400131dc  add     rsp, 40h
0x1400131e0  pop     rdi
0x1400131e1  retn
```

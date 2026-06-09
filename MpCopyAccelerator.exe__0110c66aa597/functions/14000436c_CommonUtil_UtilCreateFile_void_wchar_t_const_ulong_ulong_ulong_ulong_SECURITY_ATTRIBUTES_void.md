# CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x14000436c`
- end: `0x14000443e`
- name: `?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z`
- size: `210`
- prototype: `int(CommonUtil *__hidden this, void **, const wchar_t *, unsigned int, unsigned int, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140023664`
- `0x14002380c`
- `0x140024984`

## callees

- `0x14000436c`
- `0x14000493c`
- `0x140020220`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400043b7`
- `KERNEL32!CreateFileW` at `0x1400043b7`

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
  _QWORD *v13; // rcx
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
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return LastFailure;
    v14 = 16;
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastFailure;
    v14 = 17;
  }
  WPP_SF_Sd(v13[2], v14, (unsigned int)WPP_bed851edf8673fd54b380593fb017a56_Traceguids, v8, LastFailure);
  return LastFailure;
}

```

## disassembly

```asm
0x14000436c  mov     [rsp+arg_0], rbx
0x140004371  push    rdi
0x140004372  sub     rsp, 40h
0x140004376  mov     rax, [rsp+48h+arg_38]
0x14000437e  mov     r10d, r9d
0x140004381  mov     r9, [rsp+48h+lpSecurityAttributes]; lpSecurityAttributes
0x140004389  mov     r11d, r8d
0x14000438c  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x140004391  mov     rdi, rdx
0x140004394  mov     eax, [rsp+48h+arg_28]
0x140004398  mov     rbx, rcx
0x14000439b  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14000439f  mov     r8d, r10d; dwShareMode
0x1400043a2  mov     eax, [rsp+48h+arg_20]
0x1400043a6  mov     edx, r11d; dwDesiredAccess
0x1400043a9  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1400043b0  mov     rcx, rdi; lpFileName
0x1400043b3  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x1400043b7  call    cs:__imp_CreateFileW
0x1400043bd  mov     [rbx], rax
0x1400043c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400043c4  jz      short loc_1400043CA
0x1400043c6  xor     eax, eax
0x1400043c8  jmp     short loc_140004433
0x1400043ca  call    HrGetLastFailure
0x1400043cf  mov     ebx, eax
0x1400043d1  lea     ecx, [rax+7FF8FFFEh]
0x1400043d7  cmp     ecx, 1
0x1400043da  jbe     short loc_1400043FC
0x1400043dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043e3  lea     rax, WPP_GLOBAL_Control
0x1400043ea  cmp     rcx, rax
0x1400043ed  jz      short loc_140004431
0x1400043ef  test    byte ptr [rcx+1Ch], 1
0x1400043f3  jz      short loc_140004431
0x1400043f5  mov     edx, 11h
0x1400043fa  jmp     short loc_14000441A
0x1400043fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140004403  lea     rax, WPP_GLOBAL_Control
0x14000440a  cmp     rcx, rax
0x14000440d  jz      short loc_140004431
0x14000440f  test    byte ptr [rcx+1Ch], 4
0x140004413  jz      short loc_140004431
0x140004415  mov     edx, 10h
0x14000441a  mov     rcx, [rcx+10h]
0x14000441e  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x140004425  mov     r9, rdi
0x140004428  mov     [rsp+48h+dwCreationDisposition], ebx
0x14000442c  call    WPP_SF_Sd
0x140004431  mov     eax, ebx
0x140004433  mov     rbx, [rsp+48h+arg_0]
0x140004438  add     rsp, 40h
0x14000443c  pop     rdi
0x14000443d  retn
```

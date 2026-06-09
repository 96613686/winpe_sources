# CommonUtil::UtilCreateFile(void * *,ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x14000e990`
- end: `0x14000ea56`
- name: `?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z`
- size: `198`
- prototype: `__int64 __fastcall(CommonUtil *this, const WCHAR *, const unsigned __int16 *, __int64, unsigned int, DWORD dwFlagsAndAttributes)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140004588`
- `0x140004e84`
- `0x1400104e4`

## callees

- `0x1400071c0`
- `0x14000e990`
- `0x140011234`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14000e9cf`
- `KERNEL32!CreateFileW` at `0x14000e9cf`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilCreateFile(
        CommonUtil *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        DWORD dwFlagsAndAttributes)
{
  int v6; // edi
  HANDLE FileW; // rax
  unsigned int LastFailure; // ebx
  _QWORD *v11; // rcx
  int v12; // edx

  v6 = (int)a2;
  *(_QWORD *)this = -1;
  FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  *(_QWORD *)this = FileW;
  if ( FileW != (HANDLE)-1LL )
    return 0;
  LastFailure = HrGetLastFailure();
  if ( LastFailure + 2147024894 <= 1 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return LastFailure;
    v12 = 34;
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastFailure;
    v12 = 35;
  }
  WPP_SF_Sd(v11[2], v12, (unsigned int)&WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, v6, LastFailure);
  return LastFailure;
}

```

## disassembly

```asm
0x14000e990  mov     [rsp+arg_0], rbx
0x14000e995  push    rdi
0x14000e996  sub     rsp, 40h
0x14000e99a  mov     eax, [rsp+48h+arg_28]
0x14000e99e  mov     rdi, rdx
0x14000e9a1  xor     r9d, r9d; lpSecurityAttributes
0x14000e9a4  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14000e9ab  mov     rbx, rcx
0x14000e9ae  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14000e9b7  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14000e9bb  mov     edx, 80000000h; dwDesiredAccess
0x14000e9c0  mov     rcx, rdi; lpFileName
0x14000e9c3  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14000e9cb  lea     r8d, [r9+7]; dwShareMode
0x14000e9cf  call    cs:__imp_CreateFileW
0x14000e9d5  mov     [rbx], rax
0x14000e9d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000e9dc  jz      short loc_14000E9E2
0x14000e9de  xor     eax, eax
0x14000e9e0  jmp     short loc_14000EA4B
0x14000e9e2  call    HrGetLastFailure
0x14000e9e7  mov     ebx, eax
0x14000e9e9  lea     ecx, [rax+7FF8FFFEh]
0x14000e9ef  cmp     ecx, 1
0x14000e9f2  jbe     short loc_14000EA14
0x14000e9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9fb  lea     rax, WPP_GLOBAL_Control
0x14000ea02  cmp     rcx, rax
0x14000ea05  jz      short loc_14000EA49
0x14000ea07  test    byte ptr [rcx+1Ch], 1
0x14000ea0b  jz      short loc_14000EA49
0x14000ea0d  mov     edx, 23h ; '#'
0x14000ea12  jmp     short loc_14000EA32
0x14000ea14  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea1b  lea     rax, WPP_GLOBAL_Control
0x14000ea22  cmp     rcx, rax
0x14000ea25  jz      short loc_14000EA49
0x14000ea27  test    byte ptr [rcx+1Ch], 4
0x14000ea2b  jz      short loc_14000EA49
0x14000ea2d  mov     edx, 22h ; '"'
0x14000ea32  mov     rcx, [rcx+10h]
0x14000ea36  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000ea3d  mov     r9, rdi
0x14000ea40  mov     [rsp+48h+dwCreationDisposition], ebx
0x14000ea44  call    WPP_SF_Sd
0x14000ea49  mov     eax, ebx
0x14000ea4b  mov     rbx, [rsp+48h+arg_0]
0x14000ea50  add     rsp, 40h
0x14000ea54  pop     rdi
0x14000ea55  retn
```

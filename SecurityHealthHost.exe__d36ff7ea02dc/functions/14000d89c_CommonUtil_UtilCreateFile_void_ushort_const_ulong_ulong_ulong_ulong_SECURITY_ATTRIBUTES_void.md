# CommonUtil::UtilCreateFile(void * *,ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x14000d89c`
- end: `0x14000d961`
- name: `?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(CommonUtil *this, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ee14`

## callees

- `0x14000d89c`
- `0x14000dba8`
- `0x14000f7c8`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14000d8da`
- `KERNEL32!CreateFileW` at `0x14000d8da`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilCreateFile(CommonUtil *this, const WCHAR *a2, const unsigned __int16 *a3)
{
  int v3; // edi
  HANDLE FileW; // rax
  unsigned int LastFailure; // ebx
  _QWORD *v8; // rcx
  int v9; // edx

  v3 = (int)a2;
  *(_QWORD *)this = -1;
  FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
  *(_QWORD *)this = FileW;
  if ( FileW != (HANDLE)-1LL )
    return 0;
  LastFailure = HrGetLastFailure();
  if ( LastFailure + 2147024894 <= 1 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return LastFailure;
    v9 = 34;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastFailure;
    v9 = 35;
  }
  WPP_SF_Sd(v8[2], v9, (unsigned int)WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, v3, LastFailure);
  return LastFailure;
}

```

## disassembly

```asm
0x14000d89c  mov     rax, rsp
0x14000d89f  mov     [rax+8], rbx
0x14000d8a3  push    rdi
0x14000d8a4  sub     rsp, 40h
0x14000d8a8  mov     rdi, rdx
0x14000d8ab  mov     qword ptr [rax-18h], 0
0x14000d8b3  xor     r9d, r9d; lpSecurityAttributes
0x14000d8b6  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14000d8bd  mov     rbx, rcx
0x14000d8c0  mov     dword ptr [rax-20h], 8000000h
0x14000d8c7  mov     edx, 80000000h; dwDesiredAccess
0x14000d8cc  mov     dword ptr [rax-28h], 3
0x14000d8d3  mov     rcx, rdi; lpFileName
0x14000d8d6  lea     r8d, [r9+7]; dwShareMode
0x14000d8da  call    cs:__imp_CreateFileW
0x14000d8e0  mov     [rbx], rax
0x14000d8e3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d8e7  jz      short loc_14000D8ED
0x14000d8e9  xor     eax, eax
0x14000d8eb  jmp     short loc_14000D956
0x14000d8ed  call    HrGetLastFailure
0x14000d8f2  mov     ebx, eax
0x14000d8f4  lea     ecx, [rax+7FF8FFFEh]
0x14000d8fa  cmp     ecx, 1
0x14000d8fd  jbe     short loc_14000D91F
0x14000d8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d906  lea     rax, WPP_GLOBAL_Control
0x14000d90d  cmp     rcx, rax
0x14000d910  jz      short loc_14000D954
0x14000d912  test    byte ptr [rcx+1Ch], 1
0x14000d916  jz      short loc_14000D954
0x14000d918  mov     edx, 23h ; '#'
0x14000d91d  jmp     short loc_14000D93D
0x14000d91f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d926  lea     rax, WPP_GLOBAL_Control
0x14000d92d  cmp     rcx, rax
0x14000d930  jz      short loc_14000D954
0x14000d932  test    byte ptr [rcx+1Ch], 4
0x14000d936  jz      short loc_14000D954
0x14000d938  mov     edx, 22h ; '"'
0x14000d93d  mov     rcx, [rcx+10h]
0x14000d941  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000d948  mov     r9, rdi
0x14000d94b  mov     [rsp+48h+var_28], ebx
0x14000d94f  call    WPP_SF_Sd
0x14000d954  mov     eax, ebx
0x14000d956  mov     rbx, [rsp+48h+arg_0]
0x14000d95b  add     rsp, 40h
0x14000d95f  pop     rdi
0x14000d960  retn
```

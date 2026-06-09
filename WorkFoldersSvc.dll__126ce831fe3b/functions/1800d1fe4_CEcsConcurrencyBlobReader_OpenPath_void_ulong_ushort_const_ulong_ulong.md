# CEcsConcurrencyBlobReader::OpenPath(void * *,ulong,ushort const *,ulong,ulong)

- ea: `0x1800d1fe4`
- end: `0x1800d212b`
- name: `?OpenPath@CEcsConcurrencyBlobReader@@CAKPEAPEAXKPEBGKK@Z`
- size: `327`
- prototype: `unsigned int __fastcall(PHANDLE FileHandle, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d1cc4`

## callees

- `0x180007e10`
- `0x180011314`
- `0x1800d1fe4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800d2103`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2103`
- `ntdll!NtOpenFile` at `0x1800d20f4`
- `ntdll!NtOpenFile` at `0x1800d20f4`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800d20a4`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800d20a4`

## string_xrefs

- `0x1800d205f`: `CEcsConcurrencyBlobReader::OpenPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEcsConcurrencyBlobReader::OpenPath(PHANDLE FileHandle, __int64 a2, const unsigned __int16 *a3)
{
  _BYTE *v5; // rax
  char v6; // cl
  int inited; // eax
  ULONG v8; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-11h] BYREF
  _DWORD v12[2]; // [rsp+50h] [rbp-1h] BYREF
  char v13; // [rsp+58h] [rbp+7h]
  const char *v14; // [rsp+60h] [rbp+Fh]
  __int64 v15; // [rsp+68h] [rbp+17h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+1Fh] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
LABEL_8:
      v6 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( (v5[68] & 2) == 0 || v5[65] < 6u )
    goto LABEL_8;
  v6 = 1;
LABEL_9:
  v12[0] = 0;
  v12[1] = 220;
  v13 = v6;
  v14 = "CEcsConcurrencyBlobReader::OpenPath";
  v15 = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( FileHandle && (*FileHandle = 0, a3) )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, a3);
    if ( inited >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      inited = NtOpenFile(FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
    }
  }
  else
  {
    inited = -1073741811;
  }
  v8 = RtlNtStatusToDosError(inited);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)v12);
  return v8;
}

```

## disassembly

```asm
0x1800d1fe4  mov     [rsp-8+arg_0], rbx
0x1800d1fe9  mov     [rsp-8+arg_8], rdi
0x1800d1fee  push    rbp
0x1800d1fef  lea     rbp, [rsp-4Fh]
0x1800d1ff4  sub     rsp, 0A0h
0x1800d1ffb  mov     rdi, r8
0x1800d1ffe  mov     rbx, rcx
0x1800d2001  lea     rcx, WPP_GLOBAL_Control
0x1800d2008  mov     rax, cs:WPP_GLOBAL_Control
0x1800d200f  cmp     rax, rcx
0x1800d2012  jz      short loc_1800D203C
0x1800d2014  test    byte ptr [rax+44h], 2
0x1800d2018  jz      short loc_1800D204C
0x1800d201a  cmp     byte ptr [rax+41h], 6
0x1800d201e  jb      short loc_1800D203C
0x1800d2020  mov     edx, 11h
0x1800d2025  lea     r8, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids
0x1800d202c  mov     rcx, [rax+38h]
0x1800d2030  call    WPP_SF_
0x1800d2035  mov     rax, cs:WPP_GLOBAL_Control
0x1800d203c  test    byte ptr [rax+44h], 2
0x1800d2040  jz      short loc_1800D204C
0x1800d2042  cmp     byte ptr [rax+41h], 6
0x1800d2046  jb      short loc_1800D204C
0x1800d2048  mov     cl, 1
0x1800d204a  jmp     short loc_1800D204E
0x1800d204c  xor     cl, cl
0x1800d204e  mov     [rbp+4Fh+var_50], 0
0x1800d2055  mov     [rbp+4Fh+var_4C], 0DCh
0x1800d205c  mov     [rbp+4Fh+var_48], cl
0x1800d205f  lea     rax, aCecsconcurrenc_5; "CEcsConcurrencyBlobReader::OpenPath"
0x1800d2066  mov     [rbp+4Fh+var_40], rax
0x1800d206a  mov     [rbp+4Fh+var_38], 0
0x1800d2072  xorps   xmm0, xmm0
0x1800d2075  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800d2079  xorps   xmm1, xmm1
0x1800d207c  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm1
0x1800d2080  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800d2084  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800d2088  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d208c  test    rbx, rbx
0x1800d208f  jz      short loc_1800D20FC
0x1800d2091  mov     qword ptr [rbx], 0
0x1800d2098  test    rdi, rdi
0x1800d209b  jz      short loc_1800D20FC
0x1800d209d  mov     rdx, rdi; SourceString
0x1800d20a0  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800d20a4  call    cs:__imp_RtlInitUnicodeStringEx
0x1800d20aa  test    eax, eax
0x1800d20ac  js      short loc_1800D2101
0x1800d20ae  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800d20b5  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x1800d20bd  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800d20c4  lea     rax, [rbp+4Fh+DestinationString]
0x1800d20c8  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800d20cc  xorps   xmm0, xmm0
0x1800d20cf  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d20d4  mov     [rsp+0A0h+OpenOptions], 20h ; ' '; OpenOptions
0x1800d20dc  mov     [rsp+0A0h+ShareAccess], 7; ShareAccess
0x1800d20e4  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800d20e8  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800d20ec  mov     edx, 100000h; DesiredAccess
0x1800d20f1  mov     rcx, rbx; FileHandle
0x1800d20f4  call    cs:__imp_NtOpenFile
0x1800d20fa  jmp     short loc_1800D2101
0x1800d20fc  mov     eax, 0C000000Dh
0x1800d2101  mov     ecx, eax; Status
0x1800d2103  call    cs:__imp_RtlNtStatusToDosError
0x1800d2109  mov     ebx, eax
0x1800d210b  lea     rcx, [rbp+4Fh+var_50]; this
0x1800d210f  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800d2114  mov     eax, ebx
0x1800d2116  lea     r11, [rsp+0A0h+var_s0]
0x1800d211e  mov     rbx, [r11+10h]
0x1800d2122  mov     rdi, [r11+18h]
0x1800d2126  mov     rsp, r11
0x1800d2129  pop     rbp
0x1800d212a  retn
```

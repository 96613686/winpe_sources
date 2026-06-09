# CFileSyncReplicaMetadata::CreateFileSyncGlobalId(int,int,_SYNC_GID *)

- ea: `0x1800a1aa0`
- end: `0x1800a1c18`
- name: `?CreateFileSyncGlobalId@CFileSyncReplicaMetadata@@UEAAJHHPEAU_SYNC_GID@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(CFileSyncReplicaMetadata *__hidden this, int, int, struct _SYNC_GID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007e10`
- `0x180011314`
- `0x1800a1aa0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800a1b7b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800a1b7b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a1bc5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a1bc5`

## string_xrefs

- `0x1800a1b15`: `CFileSyncReplicaMetadata::CreateFileSyncGlobalId`

## pseudocode

```c
__int64 __fastcall CFileSyncReplicaMetadata::CreateFileSyncGlobalId(
        CFileSyncReplicaMetadata *this,
        int a2,
        int a3,
        struct _SYNC_GID *a4)
{
  _BYTE *v8; // rax
  char v9; // cl
  HRESULT Guid; // ebx
  int dwHighDateTime; // ecx
  unsigned __int64 v12; // rdx
  struct _FILETIME v13; // rax
  __int16 v14; // ax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-30h] BYREF
  int v17; // [rsp+28h] [rbp-28h] BYREF
  int v18; // [rsp+2Ch] [rbp-24h]
  char v19; // [rsp+30h] [rbp-20h]
  const char *v20; // [rsp+38h] [rbp-18h]
  __int64 v21; // [rsp+40h] [rbp-10h]
  unsigned __int64 v22; // [rsp+88h] [rbp+38h]

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, &WPP_042139e7b27436c951f7625fff162862_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( (v8[68] & 0x40) != 0 && v8[65] >= 6u )
  {
    v9 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v9 = 0;
LABEL_9:
  v18 = 1183;
  v20 = "CFileSyncReplicaMetadata::CreateFileSyncGlobalId";
  v19 = v9;
  v21 = 0;
  if ( !a4 )
  {
    Guid = -2147024809;
    v14 = 1186;
    v17 = -2147024809;
    goto LABEL_20;
  }
  v17 = 0;
  *(_OWORD *)a4 = 0;
  *((_QWORD *)a4 + 2) = 0;
  LOWORD(v18) = 1186;
  if ( !a2 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
    v12 = *((_QWORD *)this + 7);
    LODWORD(v22) = SystemTimeAsFileTime.dwLowDateTime;
    v13 = SystemTimeAsFileTime;
    if ( v12 >= *(_QWORD *)&SystemTimeAsFileTime )
    {
      v13 = (struct _FILETIME)(v12 + 1);
      LODWORD(v22) = v12 + 1;
      dwHighDateTime = (v12 + 1) >> 32;
    }
    *((struct _FILETIME *)this + 7) = v13;
    if ( a3 )
      HIDWORD(v22) = v13.dwHighDateTime & 0x7FFFFFFF;
    else
      HIDWORD(v22) = dwHighDateTime | 0x80000000;
    Guid = CoCreateGuid((GUID *)((char *)a4 + 8));
    v17 = Guid;
    v14 = 1234;
    if ( Guid >= 0 )
    {
      LOWORD(v18) = 1234;
      *(_QWORD *)a4 = _byteswap_uint64(v22);
      goto LABEL_21;
    }
LABEL_20:
    HIWORD(v18) = v14;
    goto LABEL_21;
  }
  Guid = 0;
  *(_OWORD *)a4 = CFileSyncReplicaMetadata::m_csRootGlobalId;
  *((_QWORD *)a4 + 2) = qword_1801AFB60;
LABEL_21:
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v17);
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1800a1aa0  mov     [rsp-18h+arg_0], rbx
0x1800a1aa5  mov     [rsp-18h+arg_8], rsi
0x1800a1aaa  push    rbp
0x1800a1aab  push    rdi
0x1800a1aac  push    r14
0x1800a1aae  mov     rbp, rsp
0x1800a1ab1  sub     rsp, 50h
0x1800a1ab5  mov     rdi, r9
0x1800a1ab8  mov     esi, r8d
0x1800a1abb  mov     r14d, edx
0x1800a1abe  mov     rbx, rcx
0x1800a1ac1  mov     rax, cs:WPP_GLOBAL_Control
0x1800a1ac8  lea     rcx, WPP_GLOBAL_Control
0x1800a1acf  cmp     rax, rcx
0x1800a1ad2  jz      short loc_1800A1AFC
0x1800a1ad4  test    byte ptr [rax+44h], 40h
0x1800a1ad8  jz      short loc_1800A1B0C
0x1800a1ada  cmp     byte ptr [rax+41h], 6
0x1800a1ade  jb      short loc_1800A1AFC
0x1800a1ae0  mov     rcx, [rax+38h]
0x1800a1ae4  lea     r8, WPP_042139e7b27436c951f7625fff162862_Traceguids
0x1800a1aeb  mov     edx, 26h ; '&'
0x1800a1af0  call    WPP_SF_
0x1800a1af5  mov     rax, cs:WPP_GLOBAL_Control
0x1800a1afc  test    byte ptr [rax+44h], 40h
0x1800a1b00  jz      short loc_1800A1B0C
0x1800a1b02  cmp     byte ptr [rax+41h], 6
0x1800a1b06  jb      short loc_1800A1B0C
0x1800a1b08  mov     cl, 1
0x1800a1b0a  jmp     short loc_1800A1B0E
0x1800a1b0c  xor     cl, cl
0x1800a1b0e  mov     [rbp+var_24], 49Fh
0x1800a1b15  lea     rax, aCfilesyncrepli_9; "CFileSyncReplicaMetadata::CreateFileSyn"...
0x1800a1b1c  mov     [rbp+var_18], rax
0x1800a1b20  mov     [rbp+var_20], cl
0x1800a1b23  mov     [rbp+var_10], 0
0x1800a1b2b  test    rdi, rdi
0x1800a1b2e  jz      loc_1800A1BE9
0x1800a1b34  xor     eax, eax
0x1800a1b36  xorps   xmm0, xmm0
0x1800a1b39  mov     [rbp+var_28], eax
0x1800a1b3c  movups  xmmword ptr [rdi], xmm0
0x1800a1b3f  mov     [rdi+10h], rax
0x1800a1b43  mov     eax, 4A2h
0x1800a1b48  mov     word ptr [rbp+var_24], ax
0x1800a1b4c  test    r14d, r14d
0x1800a1b4f  jz      short loc_1800A1B6F
0x1800a1b51  movups  xmm0, cs:?m_csRootGlobalId@CFileSyncReplicaMetadata@@2U_SYNC_GID@@A; _SYNC_GID CFileSyncReplicaMetadata::m_csRootGlobalId
0x1800a1b58  xor     ebx, ebx
0x1800a1b5a  movups  xmmword ptr [rdi], xmm0
0x1800a1b5d  movsd   xmm1, cs:qword_1801AFB60
0x1800a1b65  movsd   qword ptr [rdi+10h], xmm1
0x1800a1b6a  jmp     loc_1800A1BFA
0x1800a1b6f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a1b73  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800a1b7b  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a1b81  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a1b84  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800a1b87  mov     rdx, [rbx+38h]
0x1800a1b8b  mov     dword ptr [rbp+arg_18+4], ecx
0x1800a1b8e  mov     dword ptr [rbp+arg_18], eax
0x1800a1b91  mov     rax, [rbp+arg_18]
0x1800a1b95  cmp     rdx, rax
0x1800a1b98  jb      short loc_1800A1BA5
0x1800a1b9a  lea     rax, [rdx+1]
0x1800a1b9e  mov     [rbp+arg_18], rax
0x1800a1ba2  mov     ecx, dword ptr [rbp+arg_18+4]
0x1800a1ba5  mov     [rbx+38h], rax
0x1800a1ba9  test    esi, esi
0x1800a1bab  jz      short loc_1800A1BBA
0x1800a1bad  shr     rax, 20h
0x1800a1bb1  btr     eax, 1Fh
0x1800a1bb5  mov     dword ptr [rbp+arg_18+4], eax
0x1800a1bb8  jmp     short loc_1800A1BC1
0x1800a1bba  bts     ecx, 1Fh
0x1800a1bbe  mov     dword ptr [rbp+arg_18+4], ecx
0x1800a1bc1  lea     rcx, [rdi+8]; pguid
0x1800a1bc5  call    cs:__imp_CoCreateGuid
0x1800a1bcb  mov     ebx, eax
0x1800a1bcd  mov     [rbp+var_28], eax
0x1800a1bd0  test    eax, eax
0x1800a1bd2  mov     eax, 4D2h
0x1800a1bd7  js      short loc_1800A1BF6
0x1800a1bd9  mov     word ptr [rbp+var_24], ax
0x1800a1bdd  mov     rax, [rbp+arg_18]
0x1800a1be1  bswap   rax
0x1800a1be4  mov     [rdi], rax
0x1800a1be7  jmp     short loc_1800A1BFA
0x1800a1be9  mov     ebx, 80070057h
0x1800a1bee  mov     eax, 4A2h
0x1800a1bf3  mov     [rbp+var_28], ebx
0x1800a1bf6  mov     word ptr [rbp+var_24+2], ax
0x1800a1bfa  lea     rcx, [rbp+var_28]; this
0x1800a1bfe  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800a1c03  mov     rsi, [rsp+50h+arg_8]
0x1800a1c08  mov     eax, ebx
0x1800a1c0a  mov     rbx, [rsp+50h+arg_0]
0x1800a1c0f  add     rsp, 50h
0x1800a1c13  pop     r14
0x1800a1c15  pop     rdi
0x1800a1c16  pop     rbp
0x1800a1c17  retn
```

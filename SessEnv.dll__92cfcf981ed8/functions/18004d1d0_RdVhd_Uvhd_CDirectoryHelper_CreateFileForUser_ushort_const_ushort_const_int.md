# RdVhd::Uvhd::CDirectoryHelper::CreateFileForUser(ushort const *,ushort const *,int)

- ea: `0x18004d1d0`
- end: `0x18004d463`
- name: `?CreateFileForUser@CDirectoryHelper@Uvhd@RdVhd@@UEBAJPEBG0H@Z`
- size: `659`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CDirectoryHelper *this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004db0`
- `0x180017b30`
- `0x180018f8c`
- `0x180019b38`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x180032808`
- `0x180048b28`
- `0x18004d1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d33e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d3c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d33e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d3c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d43e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d43e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d430`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d430`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d329`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d329`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::CreateFileForUser(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  const unsigned __int16 *v4; // rsi
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  signed int v10; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v11; // rcx
  __int64 v12; // rdx
  unsigned __int16 *Buffer; // rax
  unsigned int v14; // r10d
  const WCHAR *v15; // rax
  RdVhd::Uvhd::CDirectoryHelper *v16; // rcx
  unsigned int v17; // r8d
  unsigned int v18; // r9d
  signed int LastError; // eax
  signed int v20; // eax
  unsigned int v22; // [rsp+28h] [rbp-51h]
  unsigned int v23; // [rsp+30h] [rbp-49h]
  void *v24; // [rsp+38h] [rbp-41h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-39h] BYREF
  struct _SECURITY_ATTRIBUTES v26; // [rsp+48h] [rbp-31h] BYREF
  const int *v27; // [rsp+60h] [rbp-19h] BYREF
  int v28; // [rsp+68h] [rbp-11h]
  __int64 v29; // [rsp+6Ch] [rbp-Dh]
  int v30; // [rsp+74h] [rbp-5h]
  __int64 v31; // [rsp+78h] [rbp-1h]
  int v32; // [rsp+80h] [rbp+7h]

  v29 = 128;
  v31 = 0;
  v27 = &CBaseStringT<unsigned short>::`vftable';
  v4 = L"D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;%s)";
  v30 = 0;
  *(_QWORD *)&v26.bInheritHandle = 0;
  v32 = 0x8000000;
  v28 = 0;
  SecurityDescriptor = 0;
  if ( !a4 )
    v4 = L"D:P(A;;FA;;;SY)(A;;FA;;;%s)";
  v7 = -1;
  *(_OWORD *)&v26.nLength = 0;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  v9 = -1;
  do
    ++v9;
  while ( v4[v9] );
  v10 = CBaseStringT<unsigned short>::EnsureSpace(&v27, (unsigned int)(v9 + v8 + 1));
  if ( v10 >= 0 )
  {
    CBaseStringT<unsigned short>::GetBufferLength(&v27);
    Buffer = (unsigned __int16 *)CBaseStringT<unsigned short>::GetBuffer(&v27);
    v10 = StringCchPrintfW(Buffer, v14, v4, a3);
    if ( v10 >= 0 )
    {
      CBaseStringT<unsigned short>::SetLength(&v27);
      v15 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v27);
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v15, 1u, &SecurityDescriptor, 0) )
        goto LABEL_28;
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError && (LastError & 0xFFFF0000) == 0 )
      {
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v10 = v10 & 0x8000FFFF | 0x50070000;
      }
      if ( v10 >= 0 )
      {
LABEL_28:
        v26.lpSecurityDescriptor = SecurityDescriptor;
        v26.nLength = 24;
        v26.bInheritHandle = 0;
        v7 = (__int64)RdVhd::Uvhd::CDirectoryHelper::CreateFileW(v16, a2, v17, v18, &v26, v22, v23, v24);
        if ( v7 == -1 )
        {
          v20 = GetLastError();
          v10 = v20;
          if ( v20 && (v20 & 0xFFFF0000) == 0 )
          {
            if ( v20 > 0 )
              v10 = (unsigned __int16)v20 | 0x80070000;
            v10 = v10 & 0x8000FFFF | 0x50080000;
          }
          if ( v10 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 41;
              goto LABEL_39;
            }
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 40;
          goto LABEL_39;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 39;
        goto LABEL_39;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 38;
LABEL_39:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, (unsigned int)v10);
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v7 != -1 )
    CloseHandle((HANDLE)v7);
  CPathString::~CPathString((CPathString *)&v27);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004d1d0  push    rbp
0x18004d1d2  push    rbx
0x18004d1d3  push    rsi
0x18004d1d4  push    rdi
0x18004d1d5  push    r12
0x18004d1d7  push    r13
0x18004d1d9  push    r14
0x18004d1db  push    r15
0x18004d1dd  lea     rbp, [rsp-1Fh]
0x18004d1e2  sub     rsp, 98h
0x18004d1e9  xor     r12d, r12d
0x18004d1ec  mov     [rbp+57h+var_64], 80h
0x18004d1f4  lea     rax, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x18004d1fb  mov     [rbp+57h+var_58], r12
0x18004d1ff  mov     [rbp+57h+var_70], rax
0x18004d203  lea     rsi, aDPAFaSyAFaBaAF; "D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;%s)"
0x18004d20a  xor     eax, eax
0x18004d20c  mov     [rbp+57h+var_5C], r12d
0x18004d210  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004d214  mov     qword ptr [rbp+57h+var_88.bInheritHandle], rax
0x18004d218  test    r9d, r9d
0x18004d21b  mov     [rbp+57h+var_50], 8000000h
0x18004d222  lea     rax, aDPAFaSyAFaS; "D:P(A;;FA;;;SY)(A;;FA;;;%s)"
0x18004d229  mov     [rbp+57h+var_68], r12d
0x18004d22d  xorps   xmm0, xmm0
0x18004d230  mov     [rbp+57h+SecurityDescriptor], r12
0x18004d234  cmovz   rsi, rax
0x18004d238  mov     r14, r8
0x18004d23b  mov     r15, rdx
0x18004d23e  mov     rdi, r13
0x18004d241  movups  xmmword ptr [rbp+57h+var_88.nLength], xmm0
0x18004d245  mov     rcx, r13
0x18004d248  inc     rcx
0x18004d24b  cmp     [r8+rcx*2], r12w
0x18004d250  jnz     short loc_18004D248
0x18004d252  mov     rax, r13
0x18004d255  inc     rax
0x18004d258  cmp     [rsi+rax*2], r12w
0x18004d25d  jnz     short loc_18004D255
0x18004d25f  lea     edx, [rcx+1]
0x18004d262  add     edx, eax
0x18004d264  lea     rcx, [rbp+57h+var_70]
0x18004d268  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x18004d26d  mov     ebx, eax
0x18004d26f  test    eax, eax
0x18004d271  jns     short loc_18004D2A8
0x18004d273  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d27a  lea     rax, WPP_GLOBAL_Control
0x18004d281  cmp     rcx, rax
0x18004d284  jz      loc_18004D427
0x18004d28a  test    byte ptr [rcx+1Ch], 4
0x18004d28e  jz      loc_18004D427
0x18004d294  cmp     byte ptr [rcx+19h], 2
0x18004d298  jb      loc_18004D427
0x18004d29e  mov     edx, 26h ; '&'
0x18004d2a3  jmp     loc_18004D414
0x18004d2a8  lea     rcx, [rbp+57h+var_70]
0x18004d2ac  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x18004d2b1  lea     rcx, [rbp+57h+var_70]
0x18004d2b5  mov     r10d, eax
0x18004d2b8  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x18004d2bd  mov     r9, r14
0x18004d2c0  mov     r8, rsi; unsigned __int16 *
0x18004d2c3  mov     edx, r10d; unsigned __int64
0x18004d2c6  mov     rcx, rax; unsigned __int16 *
0x18004d2c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d2ce  mov     ebx, eax
0x18004d2d0  test    eax, eax
0x18004d2d2  jns     short loc_18004D309
0x18004d2d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d2db  lea     rax, WPP_GLOBAL_Control
0x18004d2e2  cmp     rcx, rax
0x18004d2e5  jz      loc_18004D427
0x18004d2eb  test    byte ptr [rcx+1Ch], 4
0x18004d2ef  jz      loc_18004D427
0x18004d2f5  cmp     byte ptr [rcx+19h], 2
0x18004d2f9  jb      loc_18004D427
0x18004d2ff  mov     edx, 27h ; '''
0x18004d304  jmp     loc_18004D414
0x18004d309  lea     rcx, [rbp+57h+var_70]
0x18004d30d  call    ?SetLength@?$CBaseStringT@G@@QEAAJXZ; CBaseStringT<ushort>::SetLength(void)
0x18004d312  lea     rcx, [rbp+57h+var_70]
0x18004d316  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004d31b  xor     r9d, r9d; SecurityDescriptorSize
0x18004d31e  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18004d322  mov     rcx, rax; StringSecurityDescriptor
0x18004d325  lea     edx, [r9+1]; StringSDRevision
0x18004d329  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004d32f  mov     esi, 0FFFF0000h
0x18004d334  mov     r14d, 80070000h
0x18004d33a  test    eax, eax
0x18004d33c  jnz     short loc_18004D39A
0x18004d33e  call    cs:__imp_GetLastError
0x18004d344  mov     ebx, eax
0x18004d346  test    eax, eax
0x18004d348  jz      short loc_18004D364
0x18004d34a  test    esi, eax
0x18004d34c  jnz     short loc_18004D364
0x18004d34e  test    eax, eax
0x18004d350  jle     short loc_18004D358
0x18004d352  movzx   ebx, ax
0x18004d355  or      ebx, r14d
0x18004d358  and     ebx, 0D007FFFFh
0x18004d35e  or      ebx, 50070000h
0x18004d364  test    ebx, ebx
0x18004d366  jns     short loc_18004D39A
0x18004d368  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d36f  lea     rax, WPP_GLOBAL_Control
0x18004d376  cmp     rcx, rax
0x18004d379  jz      loc_18004D427
0x18004d37f  test    byte ptr [rcx+1Ch], 4
0x18004d383  jz      loc_18004D427
0x18004d389  cmp     byte ptr [rcx+19h], 2
0x18004d38d  jb      loc_18004D427
0x18004d393  mov     edx, 28h ; '('
0x18004d398  jmp     short loc_18004D414
0x18004d39a  mov     rax, [rbp+57h+SecurityDescriptor]
0x18004d39e  mov     rdx, r15; unsigned __int16 *
0x18004d3a1  mov     [rbp+57h+var_88.lpSecurityDescriptor], rax
0x18004d3a5  lea     rax, [rbp+57h+var_88]
0x18004d3a9  mov     [rsp+0D0h+var_B0], rax; struct _SECURITY_ATTRIBUTES *
0x18004d3ae  mov     [rbp+57h+var_88.nLength], 18h
0x18004d3b5  mov     [rbp+57h+var_88.bInheritHandle], r12d
0x18004d3b9  call    ?CreateFileW@CDirectoryHelper@Uvhd@RdVhd@@AEBAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; RdVhd::Uvhd::CDirectoryHelper::CreateFileW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18004d3be  mov     rdi, rax
0x18004d3c1  cmp     rax, r13
0x18004d3c4  jnz     short loc_18004D427
0x18004d3c6  call    cs:__imp_GetLastError
0x18004d3cc  mov     ebx, eax
0x18004d3ce  test    eax, eax
0x18004d3d0  jz      short loc_18004D3EC
0x18004d3d2  test    esi, eax
0x18004d3d4  jnz     short loc_18004D3EC
0x18004d3d6  test    eax, eax
0x18004d3d8  jle     short loc_18004D3E0
0x18004d3da  movzx   ebx, ax
0x18004d3dd  or      ebx, r14d
0x18004d3e0  and     ebx, 0D008FFFFh
0x18004d3e6  or      ebx, 50080000h
0x18004d3ec  test    ebx, ebx
0x18004d3ee  jns     short loc_18004D427
0x18004d3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d3f7  lea     rax, WPP_GLOBAL_Control
0x18004d3fe  cmp     rcx, rax
0x18004d401  jz      short loc_18004D427
0x18004d403  test    byte ptr [rcx+1Ch], 4
0x18004d407  jz      short loc_18004D427
0x18004d409  cmp     byte ptr [rcx+19h], 2
0x18004d40d  jb      short loc_18004D427
0x18004d40f  mov     edx, 29h ; ')'
0x18004d414  mov     rcx, [rcx+10h]
0x18004d418  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004d41f  mov     r9d, ebx
0x18004d422  call    WPP_SF_d
0x18004d427  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18004d42b  test    rcx, rcx
0x18004d42e  jz      short loc_18004D436
0x18004d430  call    cs:__imp_LocalFree
0x18004d436  cmp     rdi, r13
0x18004d439  jz      short loc_18004D444
0x18004d43b  mov     rcx, rdi; hObject
0x18004d43e  call    cs:__imp_CloseHandle
0x18004d444  lea     rcx, [rbp+57h+var_70]; this
0x18004d448  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004d44d  mov     eax, ebx
0x18004d44f  add     rsp, 98h
0x18004d456  pop     r15
0x18004d458  pop     r14
0x18004d45a  pop     r13
0x18004d45c  pop     r12
0x18004d45e  pop     rdi
0x18004d45f  pop     rsi
0x18004d460  pop     rbx
0x18004d461  pop     rbp
0x18004d462  retn
```

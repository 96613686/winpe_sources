# CUpdateDeploymentJob::OnUpdateProgress(ulong,ulong,ulong,ulong,uchar const *,int,int)

- ea: `0x18002a37c`
- end: `0x18002a57d`
- name: `?OnUpdateProgress@CUpdateDeploymentJob@@AEAAJKKKKPEBEHH@Z`
- size: `513`
- prototype: `__int64 __usercall@<rax>(CUpdateDeploymentJob *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, const unsigned __int8 *, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002a280`
- `0x18002bfd4`
- `0x180035ca0`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x18000dce4`
- `0x180024fd8`
- `0x180028304`
- `0x1800294e4`
- `0x18002a37c`
- `0x18002b044`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a413`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a413`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a55d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a55d`

## string_xrefs

- `0x18002a3be`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002a50b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002a52c`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUpdateDeploymentJob::OnUpdateProgress(
        CUpdateDeploymentJob *this,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *Src,
        int a7,
        int a8)
{
  __int64 v9; // rsi
  __int64 v10; // r15
  __int64 v12; // rdx
  __int64 v14; // rbp
  __int64 v15; // rsi
  __int64 v16; // rdx
  unsigned int v17; // eax
  int v18; // ecx
  int v19; // ecx
  __int64 v20; // r14
  void *v21; // rcx
  int v22; // eax
  int v23; // esi
  int v24; // [rsp+20h] [rbp-48h]
  int v25; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v9 = (unsigned int)a3;
  v10 = a2;
  if ( a2 >= *((_DWORD *)this + 172) )
  {
    v12 = 1129;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80240FFFLL,
      v24);
    return 2149847039LL;
  }
  _mm_lfence();
  if ( (unsigned int)a3 >= *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 87) + 8LL * a2) + 544LL) )
  {
    v12 = 1130;
    goto LABEL_3;
  }
  if ( a4 > 0x64 )
  {
    v12 = 1131;
    goto LABEL_3;
  }
  _mm_lfence();
  v25 = (_DWORD)this + 880;
  if ( this != (CUpdateDeploymentJob *)-880LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v14 = *(_QWORD *)(*((_QWORD *)this + 87) + 8 * v10);
  v15 = *(_QWORD *)(*(_QWORD *)(v14 + 552) + 8 * v9);
  v16 = *(unsigned int *)(v14 + 56);
  if ( a7 )
  {
    *(_QWORD *)(v15 + 92) = 0;
    *(_DWORD *)(v15 + 100) = a8;
    LOBYTE(a3) = 1;
    UpdateInstallCount(v15 + 152, v16, a3);
  }
  v17 = *(_DWORD *)(v14 + 88);
  if ( v17 != 3 )
  {
    if ( v17 > 9 || (v18 = 980, !_bittest(&v18, v17)) )
    {
      *(_DWORD *)(v14 + 88) = 5;
      v19 = *(unsigned __int16 *)(v15 + 120);
      *(_DWORD *)(v14 + 576) = a4 != v19;
      if ( (*((_DWORD *)this + 198) & 0x100) != 0 || a4 != v19 )
      {
        _mm_lfence();
        *(_WORD *)(v15 + 120) = a4;
        CUpdateDeploymentJob::CalculateTopLevelPercentComplete(this, v10);
        v20 = *(_QWORD *)(*((_QWORD *)this + 87) + 8 * v10);
        v21 = *(void **)(v20 + 168);
        if ( v21 )
        {
          SusFree(v21);
          *(_QWORD *)(v20 + 168) = 0;
        }
        v22 = DPCopyBufferWithAlloc(a5, Src, (unsigned int *)(v20 + 164), (unsigned __int8 **)(v20 + 168));
        v23 = v22;
        if ( v22 >= 0 )
          v23 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17A,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)v22,
            v25);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x48F,
            (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)v23);
        *(_BYTE *)(v14 + 432) = 1;
      }
      *((_DWORD *)this + 8) = 5;
      CUpdateDeploymentJob::AskForCallback((HANDLE *)this);
    }
  }
  if ( this != (CUpdateDeploymentJob *)-880LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  return 0;
}

```

## disassembly

```asm
0x18002a37c  mov     [rsp+arg_18], rbx
0x18002a381  push    rbp
0x18002a382  push    rsi
0x18002a383  push    rdi
0x18002a384  push    r12
0x18002a386  push    r13
0x18002a388  push    r14
0x18002a38a  push    r15
0x18002a38c  sub     rsp, 30h
0x18002a390  mov     r14d, r9d
0x18002a393  mov     esi, r8d
0x18002a396  mov     r15d, edx
0x18002a399  mov     rdi, rcx
0x18002a39c  mov     r13, [rsp+68h+Src]
0x18002a3a4  cmp     edx, [rcx+2B0h]
0x18002a3aa  jb      short loc_18002A3D1
0x18002a3ac  mov     edx, 469h; void *
0x18002a3b1  mov     ebx, 80240FFFh
0x18002a3b6  mov     rcx, [rsp+68h]; this
0x18002a3bb  mov     r9d, ebx; char *
0x18002a3be  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002a3c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a3ca  mov     eax, ebx
0x18002a3cc  jmp     loc_18002A565
0x18002a3d1  lfence
0x18002a3d4  mov     rax, [rcx+2B8h]
0x18002a3db  mov     rcx, [rax+r15*8]
0x18002a3df  cmp     esi, [rcx+220h]
0x18002a3e5  jb      short loc_18002A3EE
0x18002a3e7  mov     edx, 46Ah
0x18002a3ec  jmp     short loc_18002A3B1
0x18002a3ee  cmp     r14d, 64h ; 'd'
0x18002a3f2  jbe     short loc_18002A3FB
0x18002a3f4  mov     edx, 46Bh
0x18002a3f9  jmp     short loc_18002A3B1
0x18002a3fb  lfence
0x18002a3fe  lea     rbx, [rdi+370h]
0x18002a405  mov     qword ptr [rsp+68h+var_48], rbx; int
0x18002a40a  test    rbx, rbx
0x18002a40d  jz      short loc_18002A41A
0x18002a40f  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a413  call    cs:__imp_EnterCriticalSection
0x18002a419  nop
0x18002a41a  mov     rax, [rdi+2B8h]
0x18002a421  mov     rbp, [rax+r15*8]
0x18002a425  mov     rax, [rbp+228h]
0x18002a42c  mov     rsi, [rax+rsi*8]
0x18002a430  mov     edx, [rbp+38h]
0x18002a433  cmp     [rsp+68h+arg_30], 0
0x18002a43b  jz      short loc_18002A45E
0x18002a43d  mov     qword ptr [rsi+5Ch], 0
0x18002a445  mov     eax, [rsp+68h+arg_38]
0x18002a44c  mov     [rsi+64h], eax
0x18002a44f  lea     rcx, [rsi+98h]
0x18002a456  mov     r8b, 1
0x18002a459  call    ?UpdateInstallCount@@YAXAEAKW4tagDeploymentOperation@@_N@Z; UpdateInstallCount(ulong &,tagDeploymentOperation,bool)
0x18002a45e  mov     eax, [rbp+58h]
0x18002a461  cmp     eax, 3
0x18002a464  jz      loc_18002A554
0x18002a46a  cmp     eax, 9
0x18002a46d  ja      short loc_18002A47D
0x18002a46f  mov     ecx, 3D4h
0x18002a474  bt      ecx, eax
0x18002a477  jb      loc_18002A554
0x18002a47d  mov     dword ptr [rbp+58h], 5
0x18002a484  movzx   ecx, word ptr [rsi+78h]
0x18002a488  xor     eax, eax
0x18002a48a  cmp     r14d, ecx
0x18002a48d  setnz   al
0x18002a490  mov     [rbp+240h], eax
0x18002a496  test    dword ptr [rdi+318h], 100h
0x18002a4a0  jnz     short loc_18002A4AB
0x18002a4a2  cmp     r14d, ecx
0x18002a4a5  jz      loc_18002A544
0x18002a4ab  lfence
0x18002a4ae  mov     [rsi+78h], r14w
0x18002a4b3  mov     edx, r15d; unsigned int
0x18002a4b6  mov     rcx, rdi; this
0x18002a4b9  call    ?CalculateTopLevelPercentComplete@CUpdateDeploymentJob@@AEAAXK@Z; CUpdateDeploymentJob::CalculateTopLevelPercentComplete(ulong)
0x18002a4be  mov     rax, [rdi+2B8h]
0x18002a4c5  mov     r14, [rax+r15*8]
0x18002a4c9  lea     rsi, [r14+0A8h]
0x18002a4d0  mov     rcx, [rsi]; lpMem
0x18002a4d3  test    rcx, rcx
0x18002a4d6  jz      short loc_18002A4E4
0x18002a4d8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002a4dd  mov     qword ptr [rsi], 0
0x18002a4e4  lea     r8, [r14+0A4h]; unsigned int *
0x18002a4eb  mov     r9, rsi; unsigned __int8 **
0x18002a4ee  mov     rdx, r13; Src
0x18002a4f1  mov     ecx, [rsp+68h+arg_20]; unsigned int
0x18002a4f8  call    ?DPCopyBufferWithAlloc@@YAJKPEBEPEAKPEAPEAE@Z; DPCopyBufferWithAlloc(ulong,uchar const *,ulong *,uchar * *)
0x18002a4fd  mov     esi, eax
0x18002a4ff  test    eax, eax
0x18002a501  jns     short loc_18002A51E
0x18002a503  mov     rcx, [rsp+68h]; this
0x18002a508  mov     r9d, eax; char *
0x18002a50b  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002a512  mov     edx, 17Ah; void *
0x18002a517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a51c  jmp     short loc_18002A520
0x18002a51e  xor     esi, esi
0x18002a520  mov     rcx, [rsp+68h]; this
0x18002a525  test    esi, esi
0x18002a527  jns     short loc_18002A53D
0x18002a529  mov     r9d, esi; char *
0x18002a52c  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002a533  mov     edx, 48Fh; void *
0x18002a538  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a53d  mov     byte ptr [rbp+1B0h], 1
0x18002a544  mov     dword ptr [rdi+20h], 5
0x18002a54b  mov     rcx, rdi; this
0x18002a54e  call    ?AskForCallback@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::AskForCallback(void)
0x18002a553  nop
0x18002a554  test    rbx, rbx
0x18002a557  jz      short loc_18002A563
0x18002a559  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a55d  call    cs:__imp_LeaveCriticalSection
0x18002a563  xor     eax, eax
0x18002a565  mov     rbx, [rsp+68h+arg_18]
0x18002a56d  add     rsp, 30h
0x18002a571  pop     r15
0x18002a573  pop     r14
0x18002a575  pop     r13
0x18002a577  pop     r12
0x18002a579  pop     rdi
0x18002a57a  pop     rsi
0x18002a57b  pop     rbp
0x18002a57c  retn
```

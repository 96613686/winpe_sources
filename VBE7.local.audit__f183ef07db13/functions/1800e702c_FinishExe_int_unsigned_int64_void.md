# FinishExe(int,unsigned __int64,void * *)

- ea: `0x1800e702c`
- end: `0x1800e7918`
- name: `?FinishExe@@YAIH_KPEAPEAX@Z`
- size: `2284`
- prototype: `unsigned int __fastcall(int, unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800e2694`
- `0x1800e2920`
- `0x1800e297c`

## callees

- `0x180024478`
- `0x1800e6178`
- `0x1800e631c`
- `0x1800e64b4`
- `0x1800e702c`
- `0x180121fbc`
- `0x18013343c`
- `0x1801426d8`
- `0x18014275c`
- `0x180174ff8`
- `0x1801ac2e0`
- `0x1801ac458`
- `0x1801ac67c`
- `0x1801b0398`
- `0x180289b60`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!remove` at `0x1800e7861`
- `MSVCR100!remove` at `0x1800e7861`
- `MSVCR100!sprintf_s` at `0x1800e770e`
- `MSVCR100!sprintf_s` at `0x1800e770e`
- `MSVCR100!_mbscat_s` at `0x1800e73ee`
- `MSVCR100!_mbscat_s` at `0x1800e741a`
- `MSVCR100!_mbscat_s` at `0x1800e7437`
- `MSVCR100!_mbscat_s` at `0x1800e73ee`
- `MSVCR100!_mbscat_s` at `0x1800e741a`
- `MSVCR100!_mbscat_s` at `0x1800e7437`
- `MSVCR100!_mbscpy_s` at `0x1800e73a1`
- `MSVCR100!_mbscpy_s` at `0x1800e73a1`
- `KERNEL32!GetLastError` at `0x1800e7166`
- `KERNEL32!GetLastError` at `0x1800e7166`
- `KERNEL32!DeleteFileA` at `0x1800e78ee`
- `KERNEL32!DeleteFileA` at `0x1800e78ee`
- `KERNEL32!GetFullPathNameA` at `0x1800e715c`
- `KERNEL32!GetFullPathNameA` at `0x1800e715c`
- `KERNEL32!FreeLibrary` at `0x1800e7803`
- `KERNEL32!FreeLibrary` at `0x1800e7803`
- `KERNEL32!GetProcAddress` at `0x1800e77d0`
- `KERNEL32!GetProcAddress` at `0x1800e77d0`

## string_xrefs

- `0x1800e738a`: `LINK `
- `0x1800e7734`: `LINK.EXE`
- `0x1800e77ae`: `imagehlp.dll`

## pseudocode

```c
__int64 __fastcall FinishExe(int a1, GEN_PROJECT *a2, unsigned __int8 **a3)
{
  int v3; // eax
  int v4; // ecx
  int v5; // edx
  int v6; // r8d
  const char *v9; // [rsp+98h] [rbp-1118h]
  const char *v10; // [rsp+A0h] [rbp-1110h]
  const char *v11; // [rsp+A8h] [rbp-1108h]
  const char *v12; // [rsp+B0h] [rbp-1100h]
  const char *v13; // [rsp+B8h] [rbp-10F8h]
  LPSTR FilePart; // [rsp+C0h] [rbp-10F0h] BYREF
  __int64 v15; // [rsp+C8h] [rbp-10E8h]
  CVBAExeFile *v16; // [rsp+D0h] [rbp-10E0h]
  CVBAExeFile *v17; // [rsp+D8h] [rbp-10D8h]
  unsigned __int8 *v18; // [rsp+E0h] [rbp-10D0h]
  int v19; // [rsp+E8h] [rbp-10C8h] BYREF
  unsigned __int8 *v20; // [rsp+F0h] [rbp-10C0h]
  __int64 v21; // [rsp+F8h] [rbp-10B8h]
  CHAR FileName[2048]; // [rsp+100h] [rbp-10B0h] BYREF
  CHAR Buffer[2048]; // [rsp+900h] [rbp-8B0h] BYREF
  unsigned int i; // [rsp+1100h] [rbp-B0h]
  char v25; // [rsp+1104h] [rbp-ACh]
  char v26; // [rsp+1105h] [rbp-ABh]
  __int64 v27; // [rsp+1108h] [rbp-A8h]
  int v28; // [rsp+1110h] [rbp-A0h]
  unsigned int v29; // [rsp+1114h] [rbp-9Ch]
  unsigned __int8 *Dst; // [rsp+1118h] [rbp-98h]
  size_t SizeInBytes; // [rsp+1120h] [rbp-90h]
  signed int LastError; // [rsp+1128h] [rbp-88h]
  unsigned int v33; // [rsp+1130h] [rbp-80h]
  CVBAExeFile *v34; // [rsp+1138h] [rbp-78h]
  __int64 v35; // [rsp+1140h] [rbp-70h]
  __int64 v36; // [rsp+1148h] [rbp-68h]
  __int64 v37; // [rsp+1150h] [rbp-60h]
  HMODULE hModule; // [rsp+1158h] [rbp-58h]
  const char *v39; // [rsp+1160h] [rbp-50h]
  int v40; // [rsp+1168h] [rbp-48h]
  int v41; // [rsp+116Ch] [rbp-44h]
  FARPROC ProcAddress; // [rsp+1170h] [rbp-40h]
  const LPARAM *v43; // [rsp+1178h] [rbp-38h]
  __int64 v44; // [rsp+1180h] [rbp-30h]

  v29 = 0;
  v21 = 0;
  if ( a3 )
    *a3 = 0;
  v28 = GEN_PROJECT::Decompile(a2, 0);
  GEN_PROJECT::SetMakeExe(a2, 0);
  v27 = *((_QWORD *)g_pExeFile + 5);
  if ( v28 >= 0 && !a1 )
  {
    v41 = *((_DWORD *)g_pExeFile + 1507);
    dword_1803FC608 = v41;
    if ( (*(unsigned int (__fastcall **)(CVBAExeFile *, void *, void *, __int64))(*(_QWORD *)g_pExeFile + 16LL))(
           g_pExeFile,
           g_hexepartStart,
           &g_exeroot,
           4200) )
    {
      if ( GetFullPathNameA(*(LPCSTR *)(v27 + 32), 0x800u, Buffer, &FilePart) )
      {
        if ( FilePart )
        {
          *FilePart = 0;
          if ( (unsigned int)GetObjName(*(char **)(v27 + 32), Buffer, FileName, 0x800u) )
          {
            v29 = *((_DWORD *)g_pExeFile + 6);
            if ( !v29 )
              CVBAExeFile::Write(g_pExeFile, FileName);
            v29 = *((_DWORD *)g_pExeFile + 6);
            if ( !v29 && *(_QWORD *)(v27 + 64) )
              v29 = CVBAExeFile::WriteTypelib1To(g_pExeFile, *(const char **)(v27 + 64), &v19);
            if ( v29 )
            {
              v28 = HresultOfEberr(v29);
            }
            else
            {
              SizeInBytes = 4608;
              for ( i = 0; i < *((_DWORD *)g_pExeFile + 2); ++i )
              {
                v15 = *(_QWORD *)(*((_QWORD *)g_pExeFile + 2) + 8LL * i);
                v37 = -1;
                do
                  ++v37;
                while ( *(_BYTE *)(v15 + v37) );
                SizeInBytes += v37 + 3;
              }
              Dst = (unsigned __int8 *)ProfMemAlloc(SizeInBytes);
              if ( Dst )
              {
                _mbscpy_s(Dst, SizeInBytes, "LINK ");
                for ( i = 0; i < *((_DWORD *)g_pExeFile + 2); ++i )
                {
                  _mbscat_s(Dst, SizeInBytes, "\"");
                  _mbscat_s(Dst, SizeInBytes, *(const unsigned __int8 **)(*((_QWORD *)g_pExeFile + 2) + 8LL * i));
                  _mbscat_s(Dst, SizeInBytes, "\" ");
                }
                if ( (*(_DWORD *)(v27 + 4) & 1) != 0 && *(_QWORD *)(v27 + 72) )
                  v13 = *(const char **)(v27 + 72);
                else
                  v13 = 0;
                v39 = v13;
                if ( *(_QWORD *)(v27 + 56) )
                  v43 = *(const LPARAM **)(v27 + 56);
                else
                  v43 = &Class;
                if ( (*(_DWORD *)(v27 + 4) & 4) != 0 )
                  v11 = "/DEBUG /DEBUGTYPE:CV";
                else
                  v11 = (const char *)&Class;
                if ( (*(_DWORD *)(v27 + 4) & 2) != 0 )
                  v9 = "/DLL";
                else
                  v9 = (const char *)&Class;
                if ( (*(_DWORD *)(v27 + 4) & 8) != 0 )
                  v10 = "CONSOLE";
                else
                  v10 = "WINDOWS";
                if ( v39 )
                  v25 = 34;
                else
                  v25 = 32;
                if ( v39 )
                  v12 = v39;
                else
                  v12 = (const char *)&Class;
                if ( v39 )
                  v26 = 34;
                else
                  v26 = 32;
                v3 = *(unsigned __int16 *)(v27 + 10);
                v4 = *(unsigned __int16 *)(v27 + 8);
                v5 = *(unsigned __int16 *)(v27 + 14);
                v6 = *(unsigned __int16 *)(v27 + 12);
                v18 = Dst;
                v35 = -1;
                do
                  ++v35;
                while ( v18[v35] );
                v20 = Dst;
                v36 = -1;
                do
                  ++v36;
                while ( v20[v36] );
                sprintf_s(
                  (char *const)&Dst[v36],
                  SizeInBytes - v35,
                  "\"%s\" %c%s%c /ENTRY:%s /OUT:\"%s\" /BASE:0x%lx /SUBSYSTEM:%s,%u.%u /VERSION:%u.%u %s %s /INCREMENTAL:"
                  "NO /OPT:REF /MERGE:.rdata=.text /IGNORE:4078 %s",
                  FileName,
                  v26,
                  v12,
                  v25,
                  "__vbaS",
                  *(const char **)(v27 + 32),
                  *(_DWORD *)(v27 + 16),
                  v10,
                  v6,
                  v5,
                  v4,
                  v3,
                  v9,
                  v11,
                  (const char *)v43);
                v28 = RunConsoleApp("LINK.EXE", *(const char **)(v27 + 40), (const char *)Dst, 0, a3);
                ProfMemFree(Dst);
                if ( v28 >= 0 )
                {
                  if ( a3 && *a3 )
                  {
                    v44 = *(_QWORD *)PebappCur();
                    (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v44 + 40LL))(v44, *a3);
                    *a3 = 0;
                  }
                  ProcAddress = 0;
                  v40 = 1;
                  hModule = (HMODULE)IsolationAwareLoadLibraryA("imagehlp.dll");
                  if ( hModule )
                    ProcAddress = GetProcAddress(hModule, "BindImage");
                  if ( ProcAddress )
                    v40 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(*(_QWORD *)(v27 + 32), 0, 0);
                  if ( hModule )
                    FreeLibrary(hModule);
                }
              }
              else
              {
                v28 = -2147024882;
              }
            }
          }
          else
          {
            v28 = -2147316573;
          }
        }
        else
        {
          v28 = -2146828236;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          v33 = (unsigned __int16)LastError | 0x80070000;
        else
          v33 = LastError;
        v28 = v33;
      }
    }
    else
    {
      v28 = -2147287011;
    }
  }
  if ( (*(_DWORD *)(v27 + 4) & 0x10) == 0 )
  {
    for ( i = 0; i < *((_DWORD *)g_pExeFile + 2); ++i )
      remove(*(const char **)(*((_QWORD *)g_pExeFile + 2) + 8LL * i));
  }
  v16 = g_pExeFile;
  v34 = g_pExeFile;
  if ( g_pExeFile )
  {
    CVBAExeFile::~CVBAExeFile(v34);
    operator delete(v34);
    v17 = v34;
  }
  else
  {
    v17 = 0;
  }
  g_pExeFile = 0;
  if ( !a1 && (*(_DWORD *)(v27 + 4) & 0x10) == 0 )
    DeleteFileA(FileName);
  return EberrOfHresult((unsigned int)v28);
}

```

## disassembly

```asm
0x1800e702c  mov     [rsp-8+arg_10], r8
0x1800e7031  mov     [rsp-8+arg_8], rdx
0x1800e7036  mov     [rsp-8+arg_0], ecx
0x1800e703a  push    rbp
0x1800e703b  mov     rbp, rsp
0x1800e703e  push    rbx
0x1800e703f  push    rsi
0x1800e7040  push    rdi
0x1800e7041  mov     eax, 1198h
0x1800e7046  call    _alloca_probe
0x1800e704b  sub     rsp, rax
0x1800e704e  mov     rax, cs:__security_cookie
0x1800e7055  xor     rax, rsp
0x1800e7058  mov     [rbp+var_28], rax
0x1800e705c  mov     [rsp+11B0h+var_9C], 0
0x1800e7067  mov     [rsp+11B0h+var_10B8], 0
0x1800e7073  mov     rax, [rbp+arg_8]
0x1800e7077  mov     [rsp+11B0h+var_1120], rax
0x1800e707f  cmp     [rbp+arg_10], 0
0x1800e7084  jz      short loc_1800E7091
0x1800e7086  mov     rax, [rbp+arg_10]
0x1800e708a  mov     qword ptr [rax], 0
0x1800e7091  xor     edx, edx
0x1800e7093  mov     rcx, [rsp+11B0h+var_1120]
0x1800e709b  call    ?Decompile@GEN_PROJECT@@QEAAJW4COMPSTATE@@@Z; GEN_PROJECT::Decompile(COMPSTATE)
0x1800e70a0  mov     [rsp+11B0h+var_A0], eax
0x1800e70a7  xor     edx, edx; int
0x1800e70a9  mov     rcx, [rsp+11B0h+var_1120]; this
0x1800e70b1  call    ?SetMakeExe@GEN_PROJECT@@QEAAXH@Z; GEN_PROJECT::SetMakeExe(int)
0x1800e70b6  mov     rax, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e70bd  mov     rax, [rax+28h]
0x1800e70c1  mov     [rsp+11B0h+var_A8], rax
0x1800e70c9  cmp     [rsp+11B0h+var_A0], 0
0x1800e70d1  jl      loc_1800E7809
0x1800e70d7  cmp     [rbp+arg_0], 0
0x1800e70db  jnz     loc_1800E7809
0x1800e70e1  mov     rax, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e70e8  mov     eax, [rax+178Ch]
0x1800e70ee  mov     [rbp+var_44], eax
0x1800e70f1  mov     eax, [rbp+var_44]
0x1800e70f4  mov     cs:dword_1803FC608, eax
0x1800e70fa  mov     rax, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e7101  mov     rax, [rax]
0x1800e7104  mov     r9d, 1068h
0x1800e710a  lea     r8, ?g_exeroot@@3UepiExeRoot@@A; epiExeRoot g_exeroot
0x1800e7111  mov     rdx, cs:?g_hexepartStart@@3PEAXEA; void * g_hexepartStart
0x1800e7118  mov     rcx, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e711f  call    qword ptr [rax+10h]
0x1800e7122  test    eax, eax
0x1800e7124  jnz     short loc_1800E713B
0x1800e7126  mov     [rsp+11B0h+var_A0], 8003001Dh
0x1800e7131  jmp     loc_1800E7809
0x1800e7136  jmp     loc_1800E7809
0x1800e713b  lea     r9, [rsp+11B0h+FilePart]; lpFilePart
0x1800e7143  lea     r8, [rsp+11B0h+Buffer]; lpBuffer
0x1800e714b  mov     edx, 800h; nBufferLength
0x1800e7150  mov     rax, [rsp+11B0h+var_A8]
0x1800e7158  mov     rcx, [rax+20h]; lpFileName
0x1800e715c  call    cs:__imp_GetFullPathNameA
0x1800e7162  test    eax, eax
0x1800e7164  jnz     short loc_1800E71B5
0x1800e7166  call    cs:__imp_GetLastError
0x1800e716c  mov     [rsp+11B0h+var_88], eax
0x1800e7173  cmp     [rsp+11B0h+var_88], 0
0x1800e717b  jg      short loc_1800E7189
0x1800e717d  mov     eax, [rsp+11B0h+var_88]
0x1800e7184  mov     [rbp+var_80], eax
0x1800e7187  jmp     short loc_1800E71A1
0x1800e7189  mov     eax, [rsp+11B0h+var_88]
0x1800e7190  and     eax, 0FFFFh
0x1800e7195  or      eax, 70000h
0x1800e719a  bts     eax, 1Fh
0x1800e719e  mov     [rbp+var_80], eax
0x1800e71a1  mov     eax, [rbp+var_80]
0x1800e71a4  mov     [rsp+11B0h+var_A0], eax
0x1800e71ab  jmp     loc_1800E7809
0x1800e71b0  jmp     loc_1800E7809
0x1800e71b5  cmp     [rsp+11B0h+FilePart], 0
0x1800e71be  jnz     short loc_1800E71D5
0x1800e71c0  mov     [rsp+11B0h+var_A0], 800A0034h
0x1800e71cb  jmp     loc_1800E7809
0x1800e71d0  jmp     loc_1800E7809
0x1800e71d5  mov     rax, [rsp+11B0h+FilePart]
0x1800e71dd  mov     byte ptr [rax], 0
0x1800e71e0  mov     r9d, 800h; unsigned int
0x1800e71e6  lea     r8, [rsp+11B0h+FileName]; char *
0x1800e71ee  lea     rdx, [rsp+11B0h+Buffer]; char *
0x1800e71f6  mov     rax, [rsp+11B0h+var_A8]
0x1800e71fe  mov     rcx, [rax+20h]; char *
0x1800e7202  call    ?GetObjName@@YAHPEAD00I@Z; GetObjName(char *,char *,char *,uint)
0x1800e7207  test    eax, eax
0x1800e7209  jnz     short loc_1800E7220
0x1800e720b  mov     [rsp+11B0h+var_A0], 80028CA3h
0x1800e7216  jmp     loc_1800E7809
0x1800e721b  jmp     loc_1800E7809
0x1800e7220  mov     rax, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e7227  mov     eax, [rax+18h]
0x1800e722a  mov     [rsp+11B0h+var_9C], eax
0x1800e7231  cmp     [rsp+11B0h+var_9C], 0
0x1800e7239  jnz     short loc_1800E724F
0x1800e723b  lea     rdx, [rsp+11B0h+FileName]; char *
0x1800e7243  mov     rcx, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; this
0x1800e724a  call    ?Write@CVBAExeFile@@QEAAHPEBD@Z; CVBAExeFile::Write(char const *)
0x1800e724f  mov     rax, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e7256  mov     eax, [rax+18h]
0x1800e7259  mov     [rsp+11B0h+var_9C], eax
0x1800e7260  cmp     [rsp+11B0h+var_9C], 0
0x1800e7268  jnz     short loc_1800E72A0
0x1800e726a  mov     rax, [rsp+11B0h+var_A8]
0x1800e7272  cmp     qword ptr [rax+40h], 0
0x1800e7277  jz      short loc_1800E72A0
0x1800e7279  lea     r8, [rsp+11B0h+var_10C8]; int *
0x1800e7281  mov     rax, [rsp+11B0h+var_A8]
0x1800e7289  mov     rdx, [rax+40h]; char *
0x1800e728d  mov     rcx, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; this
0x1800e7294  call    ?WriteTypelib1To@CVBAExeFile@@QEAAIPEBDPEAH@Z; CVBAExeFile::WriteTypelib1To(char const *,int *)
0x1800e7299  mov     [rsp+11B0h+var_9C], eax
0x1800e72a0  cmp     [rsp+11B0h+var_9C], 0
0x1800e72a8  jz      short loc_1800E72C2
0x1800e72aa  mov     ecx, [rsp+11B0h+var_9C]
0x1800e72b1  call    HresultOfEberr
0x1800e72b6  mov     [rsp+11B0h+var_A0], eax
0x1800e72bd  jmp     loc_1800E7809
0x1800e72c2  mov     [rsp+11B0h+SizeInBytes], 1200h
0x1800e72ce  mov     [rsp+11B0h+var_B0], 0
0x1800e72d9  jmp     short loc_1800E72EB
0x1800e72db  mov     eax, [rsp+11B0h+var_B0]
0x1800e72e2  inc     eax
0x1800e72e4  mov     [rsp+11B0h+var_B0], eax
0x1800e72eb  mov     rax, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e72f2  mov     eax, [rax+8]
0x1800e72f5  cmp     [rsp+11B0h+var_B0], eax
0x1800e72fc  jnb     short loc_1800E7355
0x1800e72fe  mov     eax, [rsp+11B0h+var_B0]
0x1800e7305  mov     rcx, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e730c  mov     rcx, [rcx+10h]
0x1800e7310  mov     rax, [rcx+rax*8]
0x1800e7314  mov     [rsp+11B0h+var_10E8], rax
0x1800e731c  mov     [rbp+var_60], 0FFFFFFFFFFFFFFFFh
0x1800e7324  inc     [rbp+var_60]
0x1800e7328  mov     rax, [rsp+11B0h+var_10E8]
0x1800e7330  mov     rcx, [rbp+var_60]
0x1800e7334  cmp     byte ptr [rax+rcx], 0
0x1800e7338  jnz     short loc_1800E7324
0x1800e733a  mov     rax, [rbp+var_60]
0x1800e733e  mov     rcx, [rsp+11B0h+SizeInBytes]
0x1800e7346  lea     rax, [rcx+rax+3]
0x1800e734b  mov     [rsp+11B0h+SizeInBytes], rax
0x1800e7353  jmp     short loc_1800E72DB
0x1800e7355  mov     rcx, [rsp+11B0h+SizeInBytes]
0x1800e735d  call    ProfMemAlloc
0x1800e7362  mov     [rsp+11B0h+Dst], rax
0x1800e736a  cmp     [rsp+11B0h+Dst], 0
0x1800e7373  jnz     short loc_1800E738A
0x1800e7375  mov     [rsp+11B0h+var_A0], 8007000Eh
0x1800e7380  jmp     loc_1800E7809
0x1800e7385  jmp     loc_1800E7809
0x1800e738a  lea     r8, aLink; "LINK "
0x1800e7391  mov     rdx, [rsp+11B0h+SizeInBytes]; SizeInBytes
0x1800e7399  mov     rcx, [rsp+11B0h+Dst]; Dst
0x1800e73a1  call    cs:__imp__mbscpy_s
0x1800e73a7  mov     [rsp+11B0h+var_B0], 0
0x1800e73b2  jmp     short loc_1800E73C4
0x1800e73b4  mov     eax, [rsp+11B0h+var_B0]
0x1800e73bb  inc     eax
0x1800e73bd  mov     [rsp+11B0h+var_B0], eax
0x1800e73c4  mov     rax, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e73cb  mov     eax, [rax+8]
0x1800e73ce  cmp     [rsp+11B0h+var_B0], eax
0x1800e73d5  jnb     short loc_1800E7442
0x1800e73d7  lea     r8, asc_1803B2744; "\""
0x1800e73de  mov     rdx, [rsp+11B0h+SizeInBytes]; SizeInBytes
0x1800e73e6  mov     rcx, [rsp+11B0h+Dst]; Dst
0x1800e73ee  call    cs:__imp__mbscat_s
0x1800e73f4  mov     eax, [rsp+11B0h+var_B0]
0x1800e73fb  mov     rcx, cs:?g_pExeFile@@3PEAVCVBAExeFile@@EA; CVBAExeFile * g_pExeFile
0x1800e7402  mov     rcx, [rcx+10h]
0x1800e7406  mov     r8, [rcx+rax*8]; Src
0x1800e740a  mov     rdx, [rsp+11B0h+SizeInBytes]; SizeInBytes
0x1800e7412  mov     rcx, [rsp+11B0h+Dst]; Dst
0x1800e741a  call    cs:__imp__mbscat_s
0x1800e7420  lea     r8, asc_1803B2748; "\" "
0x1800e7427  mov     rdx, [rsp+11B0h+SizeInBytes]; SizeInBytes
0x1800e742f  mov     rcx, [rsp+11B0h+Dst]; Dst
0x1800e7437  call    cs:__imp__mbscat_s
0x1800e743d  jmp     loc_1800E73B4
0x1800e7442  mov     rax, [rsp+11B0h+var_A8]
0x1800e744a  mov     eax, [rax+4]
0x1800e744d  and     eax, 1
0x1800e7450  test    eax, eax
0x1800e7452  jz      short loc_1800E7479
0x1800e7454  mov     rax, [rsp+11B0h+var_A8]
0x1800e745c  cmp     qword ptr [rax+48h], 0
0x1800e7461  jz      short loc_1800E7479
0x1800e7463  mov     rax, [rsp+11B0h+var_A8]
0x1800e746b  mov     rax, [rax+48h]
0x1800e746f  mov     [rsp+11B0h+var_10F8], rax
0x1800e7477  jmp     short loc_1800E7485
0x1800e7479  mov     [rsp+11B0h+var_10F8], 0
0x1800e7485  mov     rax, [rsp+11B0h+var_10F8]
0x1800e748d  mov     [rbp+var_50], rax
0x1800e7491  mov     rax, [rsp+11B0h+var_A8]
0x1800e7499  cmp     qword ptr [rax+38h], 0
0x1800e749e  jz      short loc_1800E74B2
0x1800e74a0  mov     rax, [rsp+11B0h+var_A8]
0x1800e74a8  mov     rax, [rax+38h]
0x1800e74ac  mov     [rbp+var_38], rax
0x1800e74b0  jmp     short loc_1800E74BD
0x1800e74b2  lea     rax, Class
0x1800e74b9  mov     [rbp+var_38], rax
0x1800e74bd  mov     rax, [rsp+11B0h+var_A8]
0x1800e74c5  mov     eax, [rax+4]
0x1800e74c8  and     eax, 4
0x1800e74cb  test    eax, eax
0x1800e74cd  jz      short loc_1800E74E0
0x1800e74cf  lea     rax, aDebugDebugtype; "/DEBUG /DEBUGTYPE:CV"
0x1800e74d6  mov     [rsp+11B0h+var_1108], rax
0x1800e74de  jmp     short loc_1800E74EF
0x1800e74e0  lea     rax, Class
0x1800e74e7  mov     [rsp+11B0h+var_1108], rax
0x1800e74ef  mov     rax, [rsp+11B0h+var_A8]
0x1800e74f7  mov     eax, [rax+4]
0x1800e74fa  and     eax, 2
0x1800e74fd  test    eax, eax
0x1800e74ff  jz      short loc_1800E7512
0x1800e7501  lea     rax, aDll_1; "/DLL"
0x1800e7508  mov     [rsp+11B0h+var_1118], rax
0x1800e7510  jmp     short loc_1800E7521
0x1800e7512  lea     rax, Class
0x1800e7519  mov     [rsp+11B0h+var_1118], rax
0x1800e7521  mov     rax, [rsp+11B0h+var_A8]
0x1800e7529  mov     eax, [rax+4]
0x1800e752c  and     eax, 8
0x1800e752f  test    eax, eax
0x1800e7531  jz      short loc_1800E7544
0x1800e7533  lea     rax, aConsole; "CONSOLE"
0x1800e753a  mov     [rsp+11B0h+var_1110], rax
0x1800e7542  jmp     short loc_1800E7553
0x1800e7544  lea     rax, aWindows_0; "WINDOWS"
0x1800e754b  mov     [rsp+11B0h+var_1110], rax
0x1800e7553  cmp     [rbp+var_50], 0
0x1800e7558  jz      short loc_1800E7564
0x1800e755a  mov     [rsp+11B0h+var_AC], 22h ; '"'
0x1800e7562  jmp     short loc_1800E756C
0x1800e7564  mov     [rsp+11B0h+var_AC], 20h ; ' '
0x1800e756c  cmp     [rbp+var_50], 0
0x1800e7571  jz      short loc_1800E7581
0x1800e7573  mov     rax, [rbp+var_50]
0x1800e7577  mov     [rsp+11B0h+var_1100], rax
0x1800e757f  jmp     short loc_1800E7590
0x1800e7581  lea     rax, Class
0x1800e7588  mov     [rsp+11B0h+var_1100], rax
0x1800e7590  cmp     [rbp+var_50], 0
0x1800e7595  jz      short loc_1800E75A1
0x1800e7597  mov     [rsp+11B0h+var_AB], 22h ; '"'
0x1800e759f  jmp     short loc_1800E75A9
0x1800e75a1  mov     [rsp+11B0h+var_AB], 20h ; ' '
0x1800e75a9  mov     rax, [rsp+11B0h+var_A8]
0x1800e75b1  movzx   eax, word ptr [rax+0Ah]
0x1800e75b5  mov     rcx, [rsp+11B0h+var_A8]
0x1800e75bd  movzx   ecx, word ptr [rcx+8]
0x1800e75c1  mov     rdx, [rsp+11B0h+var_A8]
0x1800e75c9  movzx   edx, word ptr [rdx+0Eh]
0x1800e75cd  mov     r8, [rsp+11B0h+var_A8]
0x1800e75d5  movzx   r8d, word ptr [r8+0Ch]
0x1800e75da  lea     r9, aVbas; "___vbaS"
0x1800e75e1  inc     r9
0x1800e75e4  movsx   r10d, [rsp+11B0h+var_AC]
0x1800e75ed  movsx   r11d, [rsp+11B0h+var_AB]
0x1800e75f6  mov     rbx, [rsp+11B0h+Dst]
0x1800e75fe  mov     [rsp+11B0h+var_10D0], rbx
0x1800e7606  mov     [rbp+var_70], 0FFFFFFFFFFFFFFFFh
0x1800e760e  inc     [rbp+var_70]
0x1800e7612  mov     rbx, [rsp+11B0h+var_10D0]
0x1800e761a  mov     rdi, [rbp+var_70]
0x1800e761e  cmp     byte ptr [rbx+rdi], 0
0x1800e7622  jnz     short loc_1800E760E
0x1800e7624  mov     rbx, [rbp+var_70]
0x1800e7628  mov     rdi, [rsp+11B0h+SizeInBytes]
0x1800e7630  sub     rdi, rbx
0x1800e7633  mov     rbx, rdi
0x1800e7636  mov     rdi, [rsp+11B0h+Dst]
0x1800e763e  mov     [rsp+11B0h+var_10C0], rdi
0x1800e7646  mov     [rbp+var_68], 0FFFFFFFFFFFFFFFFh
0x1800e764e  inc     [rbp+var_68]
0x1800e7652  mov     rdi, [rsp+11B0h+var_10C0]
0x1800e765a  mov     rsi, [rbp+var_68]
0x1800e765e  cmp     byte ptr [rdi+rsi], 0
0x1800e7662  jnz     short loc_1800E764E
0x1800e7664  mov     rdi, [rbp+var_68]
0x1800e7668  mov     rsi, [rsp+11B0h+Dst]
0x1800e7670  add     rsi, rdi
0x1800e7673  mov     rdi, rsi
0x1800e7676  mov     rsi, [rbp+var_38]
0x1800e767a  mov     [rsp+11B0h+var_1128], rsi
0x1800e7682  mov     rsi, [rsp+11B0h+var_1108]
0x1800e768a  mov     [rsp+11B0h+var_1130], rsi
0x1800e7692  mov     rsi, [rsp+11B0h+var_1118]
0x1800e769a  mov     [rsp+11B0h+var_1138], rsi
0x1800e769f  mov     [rsp+11B0h+var_1140], eax
  ... truncated ...
```

# Vpath::removeFileInUse(Vstring const &,char)

- ea: `0x180093f80`
- end: `0x180094480`
- name: `?removeFileInUse@Vpath@@QEAAPEAVVstatus@@AEBVVstring@@D@Z`
- size: `1280`
- prototype: `struct Vstatus *__fastcall(Vpath *__hidden this, const struct Vstring *, char)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, loader_planting`

## callees

- `0x1800414c0`
- `0x180041540`
- `0x180047c50`
- `0x1800838f0`
- `0x180090560`
- `0x180090610`
- `0x180090a90`
- `0x180092780`
- `0x180092a20`
- `0x1800938a0`
- `0x180093ac0`
- `0x180093d10`
- `0x180093f80`
- `0x180094480`
- `0x180095100`
- `0x180096770`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1800bcef0`
- `0x180134070`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x180094327`
- `KERNEL32!SetFileAttributesW` at `0x180094327`
- `KERNEL32!SetFileAttributesA` at `0x18009432f`
- `KERNEL32!SetFileAttributesA` at `0x18009432f`
- `KERNEL32!MoveFileExW` at `0x18009435e`
- `KERNEL32!MoveFileExW` at `0x18009435e`
- `KERNEL32!GetLastError` at `0x180094368`
- `KERNEL32!GetLastError` at `0x180094368`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800940ef`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094120`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094151`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009421a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094278`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800942c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800943d0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094401`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009444d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800940ef`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094120`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094151`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009421a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094278`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800942c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800943d0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180094401`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009444d`

## string_xrefs

- `0x180094085`: `DeleteMe`

## pseudocode

```c
// Hidden C++ exception states: #wind=45
struct Vstatus *__fastcall Vpath::removeFileInUse(Vpath *this, const struct Vstring *a2, char a3)
{
  char isDir; // si
  struct Vstatus *result; // rax
  struct Vstatus *Dir; // rbx
  unsigned int v9; // edi
  const char *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rax
  const struct Vstring *v13; // rax
  int *v14; // rcx
  int *v15; // rcx
  int *v16; // rcx
  struct Vstatus *v17; // rax
  int *v18; // rcx
  int *v19; // rcx
  int *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  int v24; // ecx
  int v25; // ecx
  DWORD LastError; // eax
  char *v27; // rcx
  char *v28; // rcx
  int *v29; // rcx
  char *v30; // [rsp+28h] [rbp-E0h] BYREF
  char **v31; // [rsp+30h] [rbp-D8h]
  _QWORD v32[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v33[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-98h] BYREF
  __int64 v36; // [rsp+78h] [rbp-90h] BYREF
  char *v37[5]; // [rsp+80h] [rbp-88h] BYREF
  _WORD v38[256]; // [rsp+A8h] [rbp-60h] BYREF
  LPCWSTR lpFileName; // [rsp+2A8h] [rbp+1A0h]
  int v40; // [rsp+2B0h] [rbp+1A8h]
  char v41; // [rsp+2B4h] [rbp+1ACh]

  v37[3] = (char *)-2LL;
  isDir = Vpath::isDir(this);
  if ( isDir )
    result = Vpath::removeDirRecursive(this);
  else
    result = Vpath::removeFile(this);
  if ( result )
  {
    (**(void (__fastcall ***)(struct Vstatus *, __int64))result)(result, 1);
    Vpath::Vpath((Vpath *)v33, a2);
    if ( Vpath::exists((Vpath *)v33) || (Dir = Vpath::createDir((Vpath *)v33, 0)) == 0 )
    {
      v30 = dword_1802AFD5C;
      _InterlockedIncrement(&dword_1802AFD50);
      Vpath::Vpath((Vpath *)v37, this);
      v9 = 0;
      v10 = ".dll";
      if ( isDir )
        v10 = Class;
      while ( 1 )
      {
        v11 = Vitostr(&v36, v9);
        v12 = operator+(&v35, "DeleteMe", v11);
        v13 = (const struct Vstring *)operator+(&v34, v12, v10);
        Vpath::Vpath((Vpath *)v32, (const struct Vstring *)v33, v13, Class);
        v14 = (int *)(v34 - 12);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 - 12), 0xFFFFFFFF) == 1 && v14 != &dword_1802AFD50 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(v14);
          else
            free(v14);
        }
        v15 = (int *)(v35 - 12);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v35 - 12), 0xFFFFFFFF) == 1 && v15 != &dword_1802AFD50 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(v15);
          else
            free(v15);
        }
        v16 = (int *)(v36 - 12);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v36 - 12), 0xFFFFFFFF) == 1 && v16 != &dword_1802AFD50 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(v16);
          else
            free(v16);
        }
        RWCString::operator=(&v30, v32);
        v17 = Vpath::rename(v37, (const struct Vstring *)&v30, 0);
        Dir = v17;
        if ( !v17 )
          break;
        if ( (*(unsigned int (__fastcall **)(struct Vstatus *))(*(_QWORD *)v17 + 8LL))(v17) != 131097
          && (Vpath::exists((Vpath *)v33) || (Dir = Vpath::createDir((Vpath *)v33, 0)) != 0) )
        {
          Vpath::ClearStat((Vpath *)v32);
          v31 = (char **)v32;
          v19 = (int *)(v32[0] - 12LL);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32[0] - 12LL), 0xFFFFFFFF) == 1
            && v19 != &dword_1802AFD50 )
          {
            if ( dword_1802B0018 )
              COWSAllocator::Free(v19);
            else
              free(v19);
          }
          goto LABEL_61;
        }
        if ( Dir )
          (**(void (__fastcall ***)(struct Vstatus *, __int64))Dir)(Dir, 1);
        Vpath::ClearStat((Vpath *)v32);
        v31 = (char **)v32;
        v18 = (int *)(v32[0] - 12LL);
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v32[0] - 12LL)) && v18 != &dword_1802AFD50 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(v18);
          else
            free(v18);
        }
        ++v9;
      }
      Vpath::ClearStat((Vpath *)v32);
      v31 = (char **)v32;
      v20 = (int *)(v32[0] - 12LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32[0] - 12LL), 0xFFFFFFFF) == 1
        && v20 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v20);
        else
          free(v20);
      }
      lpFileName = v38;
      v40 = 512;
      v38[0] = 0;
      v41 = 0;
      sub_1800B7B38((VstackStrLCP *)v38);
      if ( a3 )
      {
        if ( (unsigned __int8)sub_180096770(v22, v21, v23) )
          v24 = *(_DWORD *)(qword_1802B00B0 + 4);
        else
          v24 = 0;
        if ( v24 == 2 )
          SetFileAttributesW(lpFileName, 2u);
        else
          SetFileAttributesA((LPCSTR)lpFileName, 2u);
      }
      if ( (unsigned __int8)sub_180096770(v22, v21, v23) )
        v25 = *(_DWORD *)(qword_1802B00B0 + 4);
      else
        v25 = 0;
      if ( v25 != 2 || MoveFileExW(lpFileName, 0, 4u) )
      {
        Dir = 0;
      }
      else
      {
        LastError = GetLastError();
        Dir = (struct Vstatus *)sub_180047C50(0x2004Eu, LastError, v30);
      }
      VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v38);
LABEL_61:
      Vpath::ClearStat((Vpath *)v37);
      v31 = v37;
      v27 = v37[0] - 12;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v37[0] - 3, 0xFFFFFFFF) == 1
        && v27 != (char *)&dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v27);
        else
          free(v27);
      }
      v28 = v30 - 12;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30 - 3, 0xFFFFFFFF) == 1
        && v28 != (char *)&dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v28);
        else
          free(v28);
      }
    }
    Vpath::ClearStat((Vpath *)v33);
    v31 = (char **)v33;
    v29 = (int *)(v33[0] - 12LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v33[0] - 12LL), 0xFFFFFFFF) == 1 && v29 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v29);
      else
        free(v29);
    }
    return Dir;
  }
  return result;
}

```

## disassembly

```asm
0x180093f80  mov     rax, rsp
0x180093f83  push    rbp
0x180093f84  push    rsi
0x180093f85  push    rdi
0x180093f86  push    r12
0x180093f88  push    r13
0x180093f8a  push    r14
0x180093f8c  push    r15
0x180093f8e  lea     rbp, [rax-1F8h]
0x180093f95  sub     rsp, 2C0h
0x180093f9c  mov     [rbp+1F0h+var_260], 0FFFFFFFFFFFFFFFEh
0x180093fa4  mov     [rax+18h], rbx
0x180093fa8  mov     rax, cs:__security_cookie
0x180093faf  xor     rax, rsp
0x180093fb2  mov     [rbp+1F0h+var_40], rax
0x180093fb9  mov     r15b, r8b
0x180093fbc  mov     rbx, rdx
0x180093fbf  mov     rdi, rcx
0x180093fc2  call    ?isDir@Vpath@@QEAADXZ; Vpath::isDir(void)
0x180093fc7  mov     sil, al
0x180093fca  xor     r12d, r12d
0x180093fcd  mov     rcx, rdi; this
0x180093fd0  test    al, al
0x180093fd2  jz      short loc_180093FDB
0x180093fd4  call    ?removeDirRecursive@Vpath@@QEAAPEAVVstatus@@XZ; Vpath::removeDirRecursive(void)
0x180093fd9  jmp     short loc_180093FE0
0x180093fdb  call    ?removeFile@Vpath@@QEAAPEAVVstatus@@XZ; Vpath::removeFile(void)
0x180093fe0  mov     rcx, rax
0x180093fe3  test    rax, rax
0x180093fe6  jz      loc_180094456
0x180093fec  mov     rax, [rcx]
0x180093fef  mov     edx, 1
0x180093ff4  mov     rax, [rax]
0x180093ff7  call    cs:__guard_dispatch_icall_fptr
0x180093ffd  mov     rdx, rbx; struct Vstring *
0x180094000  lea     rcx, [rsp+2F0h+var_2A8]; this
0x180094005  call    ??0Vpath@@QEAA@AEBVVstring@@@Z; Vpath::Vpath(Vstring const &)
0x18009400a  nop
0x18009400b  lea     rcx, [rsp+2F0h+var_2A8]; this
0x180094010  call    ?exists@Vpath@@QEAADXZ; Vpath::exists(void)
0x180094015  or      r13d, 0FFFFFFFFh
0x180094019  lea     r14, dword_1802AFD50
0x180094020  test    al, al
0x180094022  jnz     short loc_18009403C
0x180094024  xor     edx, edx; char
0x180094026  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18009402b  call    ?createDir@Vpath@@QEAAPEAVVstatus@@D@Z; Vpath::createDir(char)
0x180094030  mov     rbx, rax
0x180094033  test    rax, rax
0x180094036  jnz     loc_18009440E
0x18009403c  lea     rax, dword_1802AFD5C
0x180094043  mov     [rsp+2F0h+var_2D0], rax
0x180094048  lock inc cs:dword_1802AFD50
0x18009404f  mov     rdx, rdi; struct Vpath *
0x180094052  lea     rcx, [rsp+2F0h+var_278]; this
0x180094057  call    ??0Vpath@@QEAA@AEBV0@@Z; Vpath::Vpath(Vpath const &)
0x18009405c  nop
0x18009405d  mov     edi, r12d
0x180094060  lea     rbx, Class
0x180094067  lea     r14, aDll; ".dll"
0x18009406e  test    sil, sil
0x180094071  cmovnz  r14, rbx
0x180094075  mov     edx, edi
0x180094077  lea     rcx, [rsp+2F0h+var_280]
0x18009407c  call    ?Vitostr@@YA?AVVstring@@J@Z; Vitostr(long)
0x180094081  nop
0x180094082  mov     r8, rax
0x180094085  lea     rdx, aDeleteme; "DeleteMe"
0x18009408c  lea     rcx, [rsp+2F0h+var_288]
0x180094091  call    ??H@YA?AVVstring@@PEBDAEBV0@@Z; operator+(char const *,Vstring const &)
0x180094096  nop
0x180094097  mov     r8, r14
0x18009409a  mov     rdx, rax
0x18009409d  lea     rcx, [rsp+2F0h+var_290]
0x1800940a2  call    ??H@YA?AVVstring@@AEBV0@PEBD@Z; operator+(Vstring const &,char const *)
0x1800940a7  nop
0x1800940a8  mov     r9, rbx; char *
0x1800940ab  mov     r8, rax; struct Vstring *
0x1800940ae  lea     rdx, [rsp+2F0h+var_2A8]; struct Vstring *
0x1800940b3  lea     rcx, [rsp+2F0h+var_2C0]; this
0x1800940b8  call    ??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z; Vpath::Vpath(Vstring const &,Vstring const &,char const *)
0x1800940bd  nop
0x1800940be  mov     rcx, [rsp+2F0h+var_290]
0x1800940c3  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800940c7  mov     eax, r13d
0x1800940ca  lock xadd [rcx], eax
0x1800940ce  add     eax, r13d
0x1800940d1  lea     rsi, dword_1802AFD50
0x1800940d8  jnz     short loc_1800940F6
0x1800940da  cmp     rcx, rsi
0x1800940dd  jz      short loc_1800940F6
0x1800940df  cmp     cs:dword_1802B0018, r12d
0x1800940e6  jz      short loc_1800940EF
0x1800940e8  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800940ed  jmp     short loc_1800940F6
0x1800940ef  call    cs:free
0x1800940f5  nop
0x1800940f6  mov     rcx, [rsp+2F0h+var_288]
0x1800940fb  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800940ff  mov     eax, r13d
0x180094102  lock xadd [rcx], eax
0x180094106  add     eax, r13d
0x180094109  jnz     short loc_180094127
0x18009410b  cmp     rcx, rsi
0x18009410e  jz      short loc_180094127
0x180094110  cmp     cs:dword_1802B0018, r12d
0x180094117  jz      short loc_180094120
0x180094119  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18009411e  jmp     short loc_180094127
0x180094120  call    cs:free
0x180094126  nop
0x180094127  mov     rcx, [rsp+2F0h+var_280]
0x18009412c  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x180094130  mov     eax, r13d
0x180094133  lock xadd [rcx], eax
0x180094137  add     eax, r13d
0x18009413a  jnz     short loc_180094157
0x18009413c  cmp     rcx, rsi
0x18009413f  jz      short loc_180094157
0x180094141  cmp     cs:dword_1802B0018, r12d
0x180094148  jz      short loc_180094151
0x18009414a  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18009414f  jmp     short loc_180094157
0x180094151  call    cs:free
0x180094157  lea     rdx, [rsp+2F0h+var_2C0]
0x18009415c  lea     rcx, [rsp+2F0h+var_2D0]
0x180094161  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x180094166  xor     r8d, r8d; char
0x180094169  lea     rdx, [rsp+2F0h+var_2D0]; struct Vstring *
0x18009416e  lea     rcx, [rsp+2F0h+var_278]; this
0x180094173  call    ?rename@Vpath@@QEAAPEAVVstatus@@AEBVVstring@@D@Z; Vpath::rename(Vstring const &,char)
0x180094178  mov     rbx, rax
0x18009417b  test    rax, rax
0x18009417e  jz      loc_180094283
0x180094184  mov     rax, [rax]
0x180094187  mov     rcx, rbx
0x18009418a  mov     rax, [rax+8]
0x18009418e  call    cs:__guard_dispatch_icall_fptr
0x180094194  cmp     eax, 20019h
0x180094199  jz      short loc_1800941C1
0x18009419b  lea     rcx, [rsp+2F0h+var_2A8]; this
0x1800941a0  call    ?exists@Vpath@@QEAADXZ; Vpath::exists(void)
0x1800941a5  test    al, al
0x1800941a7  jnz     loc_18009422E
0x1800941ad  xor     edx, edx; char
0x1800941af  lea     rcx, [rsp+2F0h+var_2A8]; this
0x1800941b4  call    ?createDir@Vpath@@QEAAPEAVVstatus@@D@Z; Vpath::createDir(char)
0x1800941b9  mov     rbx, rax
0x1800941bc  test    rax, rax
0x1800941bf  jnz     short loc_18009422E
0x1800941c1  test    rbx, rbx
0x1800941c4  jz      short loc_1800941DB
0x1800941c6  mov     rax, [rbx]
0x1800941c9  mov     edx, 1
0x1800941ce  mov     rcx, rbx
0x1800941d1  mov     rax, [rax]
0x1800941d4  call    cs:__guard_dispatch_icall_fptr
0x1800941da  nop
0x1800941db  lea     rcx, [rsp+2F0h+var_2C0]; this
0x1800941e0  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x1800941e5  nop
0x1800941e6  lea     rax, [rsp+2F0h+var_2C0]
0x1800941eb  mov     [rsp+2F0h+var_2C8], rax
0x1800941f0  mov     rcx, qword ptr [rsp+2F0h+var_2C0]
0x1800941f5  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800941f9  mov     eax, r13d
0x1800941fc  lock xadd [rcx], eax
0x180094200  add     eax, r13d
0x180094203  jnz     short loc_180094220
0x180094205  cmp     rcx, rsi
0x180094208  jz      short loc_180094220
0x18009420a  cmp     cs:dword_1802B0018, r12d
0x180094211  jz      short loc_18009421A
0x180094213  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180094218  jmp     short loc_180094220
0x18009421a  call    cs:free
0x180094220  inc     edi
0x180094222  lea     rbx, Class
0x180094229  jmp     loc_180094075
0x18009422e  lea     rcx, [rsp+2F0h+var_2C0]; this
0x180094233  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180094238  nop
0x180094239  lea     rax, [rsp+2F0h+var_2C0]
0x18009423e  mov     [rsp+2F0h+var_2C8], rax
0x180094243  mov     rcx, qword ptr [rsp+2F0h+var_2C0]
0x180094248  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18009424c  mov     eax, r13d
0x18009424f  lock xadd [rcx], eax
0x180094253  add     eax, r13d
0x180094256  jnz     loc_180094391
0x18009425c  cmp     rcx, rsi
0x18009425f  jz      loc_180094391
0x180094265  cmp     cs:dword_1802B0018, r12d
0x18009426c  jz      short loc_180094278
0x18009426e  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180094273  jmp     loc_180094391
0x180094278  call    cs:free
0x18009427e  jmp     loc_180094391
0x180094283  lea     rcx, [rsp+2F0h+var_2C0]; this
0x180094288  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x18009428d  nop
0x18009428e  lea     rax, [rsp+2F0h+var_2C0]
0x180094293  mov     [rsp+2F0h+var_2C8], rax
0x180094298  mov     rcx, qword ptr [rsp+2F0h+var_2C0]
0x18009429d  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800942a1  mov     eax, r13d
0x1800942a4  lock xadd [rcx], eax
0x1800942a8  add     eax, r13d
0x1800942ab  jnz     short loc_1800942C8
0x1800942ad  cmp     rcx, rsi
0x1800942b0  jz      short loc_1800942C8
0x1800942b2  cmp     cs:dword_1802B0018, r12d
0x1800942b9  jz      short loc_1800942C2
0x1800942bb  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800942c0  jmp     short loc_1800942C8
0x1800942c2  call    cs:free
0x1800942c8  lea     rax, [rbp+1F0h+var_250]
0x1800942cc  mov     [rbp+1F0h+lpFileName], rax
0x1800942d3  mov     [rbp+1F0h+var_48], 200h
0x1800942dd  mov     [rbp+1F0h+var_250], r12w
0x1800942e2  mov     [rbp+1F0h+var_44], r12b
0x1800942e9  lea     rdx, [rsp+2F0h+var_2D0]
0x1800942ee  lea     rcx, [rbp+1F0h+var_250]; this
0x1800942f2  call    sub_1800B7B38
0x1800942f7  nop
0x1800942f8  mov     ebx, 2
0x1800942fd  test    r15b, r15b
0x180094300  jz      short loc_180094335
0x180094302  call    sub_180096770
0x180094307  test    al, al
0x180094309  jz      short loc_180094317
0x18009430b  mov     rax, cs:qword_1802B00B0
0x180094312  mov     ecx, [rax+4]
0x180094315  jmp     short loc_18009431A
0x180094317  mov     ecx, r12d
0x18009431a  mov     edx, ebx; dwFileAttributes
0x18009431c  cmp     ecx, ebx
0x18009431e  mov     rcx, [rbp+1F0h+lpFileName]; lpFileName
0x180094325  jnz     short loc_18009432F
0x180094327  call    cs:SetFileAttributesW
0x18009432d  jmp     short loc_180094335
0x18009432f  call    cs:SetFileAttributesA
0x180094335  call    sub_180096770
0x18009433a  test    al, al
0x18009433c  jz      short loc_18009434A
0x18009433e  mov     rax, cs:qword_1802B00B0
0x180094345  mov     ecx, [rax+4]
0x180094348  jmp     short loc_18009434D
0x18009434a  mov     ecx, r12d
0x18009434d  cmp     ecx, ebx
0x18009434f  jnz     short loc_180094384
0x180094351  xor     edx, edx; lpNewFileName
0x180094353  lea     r8d, [rdx+4]; dwFlags
0x180094357  mov     rcx, [rbp+1F0h+lpFileName]; lpExistingFileName
0x18009435e  call    cs:MoveFileExW
0x180094364  test    eax, eax
0x180094366  jnz     short loc_180094384
0x180094368  call    cs:GetLastError
0x18009436e  mov     r8, [rsp+2F0h+var_2D0]
0x180094373  mov     edx, eax
0x180094375  mov     ecx, 2004Eh
0x18009437a  call    sub_180047C50
0x18009437f  mov     rbx, rax
0x180094382  jmp     short loc_180094387
0x180094384  mov     rbx, r12
0x180094387  lea     rcx, [rbp+1F0h+var_250]; this
0x18009438b  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x180094390  nop
0x180094391  lea     rcx, [rsp+2F0h+var_278]; this
0x180094396  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x18009439b  nop
0x18009439c  lea     rax, [rsp+2F0h+var_278]
0x1800943a1  mov     [rsp+2F0h+var_2C8], rax
0x1800943a6  mov     rcx, qword ptr [rsp+2F0h+var_278]
0x1800943ab  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800943af  mov     eax, r13d
0x1800943b2  lock xadd [rcx], eax
0x1800943b6  add     eax, r13d
0x1800943b9  jnz     short loc_1800943D7
0x1800943bb  cmp     rcx, rsi
0x1800943be  jz      short loc_1800943D7
0x1800943c0  cmp     cs:dword_1802B0018, r12d
0x1800943c7  jz      short loc_1800943D0
0x1800943c9  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800943ce  jmp     short loc_1800943D7
0x1800943d0  call    cs:free
0x1800943d6  nop
0x1800943d7  mov     rcx, [rsp+2F0h+var_2D0]
0x1800943dc  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800943e0  mov     eax, r13d
0x1800943e3  lock xadd [rcx], eax
0x1800943e7  add     eax, r13d
0x1800943ea  jnz     short loc_180094407
0x1800943ec  cmp     rcx, rsi
0x1800943ef  jz      short loc_180094407
0x1800943f1  cmp     cs:dword_1802B0018, r12d
0x1800943f8  jz      short loc_180094401
0x1800943fa  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800943ff  jmp     short loc_180094407
0x180094401  call    cs:free
  ... truncated ...
```

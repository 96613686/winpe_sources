# DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)

- ea: `0x18000f8dc`
- end: `0x18000fafc`
- name: `?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z`
- size: `544`
- prototype: `void __fastcall(struct ITmInstance *, unsigned __int16, unsigned __int16, unsigned int, int, int, unsigned int, void *, char *, int, void *)`
- caller_count: `10`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005220`
- `0x18000abb0`
- `0x18000adb0`
- `0x180017fe8`
- `0x180026360`
- `0x180027500`
- `0x18002c3f8`
- `0x1800490e0`
- `0x1800ac080`
- `0x1800b5b84`

## callees

- `0x180007d08`
- `0x18000f8dc`
- `0x180013dc8`
- `0x180013e24`
- `0x1800240fc`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f953`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f953`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18000f95b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18000f95b`
- `msvcrt!mbstowcs` at `0x18000fa34`
- `msvcrt!mbstowcs` at `0x18000fa75`
- `msvcrt!mbstowcs` at `0x18000fa34`
- `msvcrt!mbstowcs` at `0x18000fa75`

## pseudocode

```c
void __fastcall DELLog(
        struct ITmInstance *a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned int a4,
        int a5,
        int a6,
        unsigned int a7,
        void *a8,
        char *a9,
        int a10)
{
  DWORD CurrentProcessId; // ebx
  const char *CommandLineA; // rax
  unsigned __int16 **v16; // rax
  void *v17; // r9
  unsigned __int16 **v18; // rbx
  __int16 v19; // si
  __int64 v20; // rax
  size_t v21; // r15
  size_t v22; // rax
  size_t v23; // r14
  wchar_t *v24; // rax
  size_t Size; // [rsp+28h] [rbp-1E0h]
  char *Source; // [rsp+58h] [rbp-1B0h] BYREF
  void *Src; // [rsp+60h] [rbp-1A8h]
  char v29[320]; // [rsp+70h] [rbp-198h] BYREF

  Src = a8;
  memset_0(v29, 0, 0x136u);
  Source = v29;
  if ( a6 )
  {
    CurrentProcessId = GetCurrentProcessId();
    CommandLineA = GetCommandLineA();
    StringCchPrintfA(
      v29,
      0x136u,
      "hr = 0x%08x, %s:%d, CmdLine: %s, Pid: %d",
      a5,
      a9,
      a10,
      CommandLineA,
      CurrentProcessId);
  }
  if ( a1 )
  {
    LOWORD(Size) = 1;
    (*(void (__fastcall **)(struct ITmInstance *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, unsigned int, char **, void *))(*(_QWORD *)a1 + 448LL))(
      a1,
      a2,
      a3,
      a4,
      0,
      Size,
      a7,
      &Source,
      a8);
  }
  else
  {
    v16 = (unsigned __int16 **)operator new[](8u);
    v18 = v16;
    if ( v16 )
    {
      *v16 = 0;
      v19 = 0;
      v20 = -1;
      while ( !v19 )
      {
        if ( Source )
        {
          do
            ++v20;
          while ( Source[v20] );
          v21 = v20 + 1;
          v22 = mbstowcs(0, Source, v20 + 1);
          v23 = v22;
          if ( v22 == -1 )
            goto LABEL_16;
          v24 = (wchar_t *)operator new[](saturated_mul(v22 + 1, 2u));
          *v18 = v24;
          if ( !v24 || mbstowcs(v24, Source, v21) != v23 )
            goto LABEL_16;
          v20 = -1;
          (*v18)[v23] = 0;
        }
        v19 = 1;
      }
      LODWORD(Size) = a7;
      DtcWriteToEventLoggerExW(a2, a3, a4, v17, 1u, Size, v18, Src, 0);
LABEL_16:
      FreeWideStringArray(v18);
    }
  }
}

```

## disassembly

```asm
0x18000f8dc  push    rbx
0x18000f8de  push    rbp
0x18000f8df  push    rsi
0x18000f8e0  push    rdi
0x18000f8e1  push    r12
0x18000f8e3  push    r13
0x18000f8e5  push    r14
0x18000f8e7  push    r15
0x18000f8e9  sub     rsp, 1C8h
0x18000f8f0  mov     rax, cs:__security_cookie
0x18000f8f7  xor     rax, rsp
0x18000f8fa  mov     [rsp+208h+var_58], rax
0x18000f902  mov     r14, [rsp+208h+arg_38]
0x18000f90a  movzx   r13d, r8w
0x18000f90e  mov     rdi, [rsp+208h+arg_40]
0x18000f916  movzx   r12d, dx
0x18000f91a  mov     rsi, rcx
0x18000f91d  mov     [rsp+208h+var_1A8], r14
0x18000f922  xor     edx, edx; Val
0x18000f924  mov     [rsp+208h+var_1B8], r9d
0x18000f929  mov     r8d, 136h; Size
0x18000f92f  lea     rcx, [rsp+208h+var_198]; void *
0x18000f934  mov     ebp, r9d
0x18000f937  call    memset_0
0x18000f93c  xor     r15d, r15d
0x18000f93f  lea     rax, [rsp+208h+var_198]
0x18000f944  mov     [rsp+208h+Source], rax
0x18000f949  cmp     [rsp+208h+arg_28], r15d
0x18000f951  jz      short loc_18000F998
0x18000f953  call    cs:__imp_GetCurrentProcessId
0x18000f959  mov     ebx, eax
0x18000f95b  call    cs:__imp_GetCommandLineA
0x18000f961  mov     r9d, [rsp+208h+arg_20]
0x18000f969  lea     r8, aHr0x08xSDCmdli; "hr = 0x%08x, %s:%d, CmdLine: %s, Pid: %"...
0x18000f970  mov     dword ptr [rsp+208h+Src], ebx
0x18000f974  lea     rcx, [rsp+208h+var_198]; char *
0x18000f979  mov     [rsp+208h+var_1D8], rax
0x18000f97e  mov     edx, 136h; unsigned __int64
0x18000f983  mov     eax, [rsp+208h+arg_48]
0x18000f98a  mov     dword ptr [rsp+208h+Size], eax
0x18000f98e  mov     qword ptr [rsp+208h+var_1E8], rdi
0x18000f993  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f998  test    rsi, rsi
0x18000f99b  jz      short loc_18000F9E7
0x18000f99d  mov     rax, [rsi]
0x18000f9a0  lea     rcx, [rsp+208h+Source]
0x18000f9a5  mov     r10d, dword ptr [rsp+208h+arg_30]
0x18000f9ad  mov     r9d, ebp
0x18000f9b0  mov     qword ptr [rsp+208h+var_1C8], r14
0x18000f9b5  movzx   r8d, r13w
0x18000f9b9  mov     [rsp+208h+Src], rcx
0x18000f9be  movzx   edx, r12w
0x18000f9c2  mov     rax, [rax+1C0h]
0x18000f9c9  mov     rcx, rsi
0x18000f9cc  mov     dword ptr [rsp+208h+var_1D8], r10d
0x18000f9d1  mov     word ptr [rsp+208h+Size], 1
0x18000f9d8  mov     qword ptr [rsp+208h+var_1E8], r15
0x18000f9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9e2  jmp     loc_18000FAD8
0x18000f9e7  mov     ecx, 8; unsigned __int64
0x18000f9ec  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f9f1  mov     rbx, rax
0x18000f9f4  test    rax, rax
0x18000f9f7  jz      loc_18000FAD8
0x18000f9fd  mov     [rax], r15
0x18000fa00  mov     esi, r15d
0x18000fa03  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fa07  mov     edi, 1
0x18000fa0c  cmp     si, di
0x18000fa0f  jnb     loc_18000FA98
0x18000fa15  movzx   ebp, si
0x18000fa18  mov     rdx, [rsp+rbp*8+208h+Source]; Source
0x18000fa1d  test    rdx, rdx
0x18000fa20  jz      short loc_18000FA90
0x18000fa22  inc     rax
0x18000fa25  cmp     [rdx+rax], r15b
0x18000fa29  jnz     short loc_18000FA22
0x18000fa2b  lea     r15, [rax+1]
0x18000fa2f  xor     ecx, ecx; Dest
0x18000fa31  mov     r8, r15; MaxCount
0x18000fa34  call    cs:__imp_mbstowcs
0x18000fa3a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fa3e  mov     r14, rax
0x18000fa41  cmp     rax, r8
0x18000fa44  jz      loc_18000FACE
0x18000fa4a  lea     rcx, [rax+1]
0x18000fa4e  lea     eax, [r8+3]
0x18000fa52  mul     rcx
0x18000fa55  cmovb   rax, r8
0x18000fa59  mov     rcx, rax; unsigned __int64
0x18000fa5c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fa61  mov     [rbx+rbp*8], rax
0x18000fa65  test    rax, rax
0x18000fa68  jz      short loc_18000FACE
0x18000fa6a  mov     rdx, [rsp+rbp*8+208h+Source]; Source
0x18000fa6f  mov     r8, r15; MaxCount
0x18000fa72  mov     rcx, rax; Dest
0x18000fa75  call    cs:__imp_mbstowcs
0x18000fa7b  cmp     rax, r14
0x18000fa7e  jnz     short loc_18000FACE
0x18000fa80  mov     rcx, [rbx+rbp*8]
0x18000fa84  xor     r15d, r15d
0x18000fa87  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fa8b  mov     [rcx+r14*2], r15w
0x18000fa90  add     si, di
0x18000fa93  jmp     loc_18000FA0C
0x18000fa98  mov     rax, [rsp+208h+var_1A8]
0x18000fa9d  movzx   edx, r13w; unsigned __int16
0x18000faa1  mov     r8d, [rsp+208h+var_1B8]; unsigned int
0x18000faa6  movzx   ecx, r12w; unsigned __int16
0x18000faaa  mov     [rsp+208h+var_1C8], r15d; int
0x18000faaf  mov     [rsp+208h+Src], rax; Src
0x18000fab4  mov     eax, dword ptr [rsp+208h+arg_30]
0x18000fabb  mov     [rsp+208h+var_1D8], rbx; unsigned __int16 **
0x18000fac0  mov     dword ptr [rsp+208h+Size], eax; Size
0x18000fac4  mov     [rsp+208h+var_1E8], di; unsigned __int16
0x18000fac9  call    ?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x18000face  mov     edx, edi
0x18000fad0  mov     rcx, rbx; Block
0x18000fad3  call    FreeWideStringArray
0x18000fad8  mov     rcx, [rsp+208h+var_58]
0x18000fae0  xor     rcx, rsp; StackCookie
0x18000fae3  call    __security_check_cookie
0x18000fae8  add     rsp, 1C8h
0x18000faef  pop     r15
0x18000faf1  pop     r14
0x18000faf3  pop     r13
0x18000faf5  pop     r12
0x18000faf7  pop     rdi
0x18000faf8  pop     rsi
0x18000faf9  pop     rbp
0x18000fafa  pop     rbx
0x18000fafb  retn
```

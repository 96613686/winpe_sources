# mkl_ueaa_init

- ea: `0x180453fc0`
- end: `0x180454440`
- name: `mkl_ueaa_init`
- size: `1152`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x18012d290`

## callees

- `0x18000e590`
- `0x180055ce0`
- `0x180055e50`
- `0x180056180`
- `0x1802405f0`
- `0x180453fc0`
- `0x180454440`
- `0x180454500`
- `0x180480f10`
- `0x180480f70`
- `0x180481030`
- `0x180481130`
- `0x180481160`
- `0x1832ce3b0`
- `0x1832ceb40`
- `0x1832dbf20`
- `0x1832dbf30`
- `0x1832dbf90`
- `0x1832dc0d0`
- `0x1832dc0e0`

## string_xrefs

- `0x180454055`: `LD_LIBRARY_PATH`
- `0x18045424b`: `LD_LIBRARY_PATH`
- `0x1804542a6`: `LD_LIBRARY_PATH`
- `0x18045404e`: `MIC_LD_LIBRARY_PATH`
- `0x180454244`: `MIC_LD_LIBRARY_PATH`
- `0x1804542ad`: `MIC_LD_LIBRARY_PATH`

## pseudocode

```c
__int64 __fastcall mkl_ueaa_init(const char *a1)
{
  void *v1; // rsp
  unsigned int v3; // esi
  char *v4; // r13
  int v6; // eax
  const char *v7; // rcx
  char *v8; // r15
  __int64 v9; // rdi
  __int64 v10; // r12
  char *v11; // rax
  char *v12; // rdi
  char *v13; // rax
  __int64 v14; // rdi
  unsigned int v15; // ebx
  int i; // ebx
  int v17; // r14d
  int v18; // esi
  void *v19; // rsp
  int v20; // eax
  const char *v21; // rcx
  int v22; // eax
  const char *v23; // rcx
  int v24; // eax
  char *v25; // r12
  __int64 v26; // rdi
  __int64 v27; // rdi
  char *v28; // rax
  char *v29; // r15
  char *v30; // rax
  char *Context; // [rsp+30h] [rbp+0h] BYREF
  char *v32; // [rsp+38h] [rbp+8h] BYREF
  int v33; // [rsp+40h] [rbp+10h]
  _DWORD v34[3]; // [rsp+50h] [rbp+20h] BYREF
  _BYTE v35[32316]; // [rsp+5Ch] [rbp+2Ch] BYREF
  _BYTE v36[4096]; // [rsp+7E98h] [rbp+7E68h] BYREF
  char v37[4096]; // [rsp+8E98h] [rbp+8E68h] BYREF
  char Source[4096]; // [rsp+9E98h] [rbp+9E68h] BYREF
  _stat64i32 Stat; // [rsp+AE98h] [rbp+AE68h] BYREF
  struct _stat64i32 v40; // [rsp+AEC8h] [rbp+AE98h] BYREF

  v1 = alloca(44800);
  v3 = -1;
  v4 = 0;
  if ( mkl_ueaa_initialized )
    return 0;
  if ( !(unsigned int)mkl_be_init() && a1 )
  {
    if ( *a1 == 47 )
    {
      v4 = strdup_0(a1);
    }
    else
    {
      v6 = mkl_serv_default_progress();
      v7 = "LD_LIBRARY_PATH";
      if ( !v6 )
        v7 = "MIC_LD_LIBRARY_PATH";
      mkl_serv_getenv(v7, Source, 4096);
      v8 = strdup_0(Source);
      v9 = mkl_serv_strnlen_s(Source, 260);
      v10 = v9 + mkl_serv_strnlen_s(a1, 260) + 2;
      v11 = (char *)malloc_0(v10);
      v12 = v11;
      if ( v8 )
      {
        if ( v11 )
        {
          v13 = strtok_s_0(v8, off_1836E2140, &Context);
          if ( v13 )
          {
            while ( 1 )
            {
              mkl_serv_sprintf_s((__int64)v12, v10, (__int64)"%s/%s", v13, a1);
              if ( !stat64i32_0(v12, &Stat) && (Stat.st_mode & 0x8000) != 0 )
                break;
              v13 = strtok_s_0(0, off_1836E2140, &Context);
              if ( !v13 )
                goto LABEL_15;
            }
            v4 = strdup_0(v12);
          }
        }
      }
LABEL_15:
      free_0(v12);
      free_0(v8);
      mkl_serv_getenv("MKLROOT", Source, 4096);
      if ( !v4 )
      {
        v4 = 0;
        v25 = strdup_0(Source);
        v26 = mkl_serv_strnlen_s(Source, 260);
        v27 = v26 + mkl_serv_strnlen_s(a1, 260) + 2;
        v28 = (char *)malloc_0(v27);
        v29 = v28;
        if ( v25 )
        {
          if ( v28 )
          {
            v30 = strtok_s_0(v25, off_1836E2140, &v32);
            if ( v30 )
            {
              while ( 1 )
              {
                mkl_serv_sprintf_s((__int64)v29, v27, (__int64)"%s/%s", v30, a1);
                if ( !stat64i32_0(v29, &v40) && (v40.st_mode & 0x8000) != 0 )
                  break;
                v30 = strtok_s_0(0, off_1836E2140, &v32);
                if ( !v30 )
                  goto LABEL_45;
              }
              v4 = strdup_0(v29);
            }
          }
        }
LABEL_45:
        free_0(v29);
        free_0(v25);
      }
    }
    if ( v4 )
    {
      mkl_ueaa_device = 0;
      mkl_ueaa_devices = mkl_ueaa_prv_read_env();
      v14 = 0;
      v15 = 1;
      v33 = -1;
      while ( 1 )
      {
        if ( *((_DWORD *)&mkl_ueaa_device_mask + v14 + 1) )
        {
          v17 = -1;
          v18 = mkl_ueaa_devices;
          v19 = alloca(sizeof_be_device_t);
          v20 = mkl_serv_default_progress();
          v21 = "LD_LIBRARY_PATH";
          if ( !v20 )
            v21 = "MIC_LD_LIBRARY_PATH";
          mkl_serv_getenv(v21, v37, 4096);
          if ( !(unsigned int)mkl_be_device_init(&Context, (unsigned int)v14, v4, v37) )
          {
            mkl_be_fill_externs_from_device_struct(&Context, v15);
            v34[0] = 6;
            v34[1] = v15;
            v34[2] = v18;
            v35[0] = 0;
            v22 = mkl_serv_default_progress();
            v23 = "LD_LIBRARY_PATH";
            if ( !v22 )
              v23 = "MIC_LD_LIBRARY_PATH";
            v24 = mkl_serv_getenv(v23, v36, 4096);
            if ( v24 > 0
              && !(unsigned int)mkl_serv_strncpy_s(v35, 4096, v36, v24)
              && !(unsigned int)mkl_ueaa_prv_invoke_task(v34, 0, 0, v15) )
            {
              v17 = mkl_ueaa_prv_sync_task(v15, 1);
              if ( v17 )
                v17 = -1;
            }
          }
          if ( v17 )
          {
            v3 = v33;
            break;
          }
          ++v15;
        }
        if ( ++v14 >= 32 )
        {
          v3 = 0;
          mkl_ueaa_initialized = 1;
          break;
        }
      }
    }
  }
  free_0(v4);
  if ( v3 )
  {
    for ( i = 1; i < mkl_ueaa_devices; ++i )
      mkl_be_device_fini((unsigned int)i);
  }
  return v3;
}

```

## disassembly

```asm
0x180453fc0  push    rbp
0x180453fc1  push    rbx
0x180453fc2  push    rsi
0x180453fc3  push    rdi
0x180453fc4  push    r12
0x180453fc6  push    r13
0x180453fc8  push    r15
0x180453fca  mov     eax, 0AF00h
0x180453fcf  call    _alloca_probe
0x180453fd4  sub     rsp, 0AF00h
0x180453fdb  lea     rbp, [rsp+30h]
0x180453fe0  mov     rbx, rcx
0x180453fe3  mov     rax, cs:__security_cookie
0x180453fea  mov     esi, 0FFFFFFFFh
0x180453fef  xor     rax, rbp
0x180453ff2  xor     r13d, r13d
0x180453ff5  mov     [rbp+0AF00h+var_38], rax
0x180453ffc  cmp     cs:mkl_ueaa_initialized, 0
0x180454003  jz      short loc_180454028
0x180454005  mov     rcx, [rbp+0AF00h+var_38]
0x18045400c  xor     rcx, rbp; StackCookie
0x18045400f  call    __security_check_cookie
0x180454014  xor     eax, eax
0x180454016  lea     rsp, [rbp+0AED0h]
0x18045401d  pop     r15
0x18045401f  pop     r13
0x180454021  pop     r12
0x180454023  pop     rdi
0x180454024  pop     rsi
0x180454025  pop     rbx
0x180454026  pop     rbp
0x180454027  retn
0x180454028  call    mkl_be_init
0x18045402d  test    eax, eax
0x18045402f  jnz     loc_1804541C8
0x180454035  test    rbx, rbx
0x180454038  jz      loc_1804541C8
0x18045403e  cmp     byte ptr [rbx], 2Fh ; '/'
0x180454041  jz      loc_180454426
0x180454047  call    mkl_serv_default_progress
0x18045404c  test    eax, eax
0x18045404e  lea     rdi, aMicLdLibraryPa; "MIC_LD_LIBRARY_PATH"
0x180454055  lea     rcx, aLdLibraryPath; "LD_LIBRARY_PATH"
0x18045405c  lea     rdx, [rbp+0AF00h+Source]
0x180454063  cmovz   rcx, rdi
0x180454067  mov     r8d, 1000h
0x18045406d  call    mkl_serv_getenv
0x180454072  lea     rcx, [rbp+0AF00h+Source]; Source
0x180454079  call    _strdup_0
0x18045407e  mov     r15, rax
0x180454081  mov     edx, 104h
0x180454086  lea     rcx, [rbp+0AF00h+Source]
0x18045408d  call    mkl_serv_strnlen_s
0x180454092  mov     rdi, rax
0x180454095  mov     rcx, rbx
0x180454098  mov     edx, 104h
0x18045409d  call    mkl_serv_strnlen_s
0x1804540a2  lea     r12, [rdi+rax+2]
0x1804540a7  mov     rcx, r12; Size
0x1804540aa  call    malloc_0
0x1804540af  mov     rdi, rax
0x1804540b2  test    r15, r15
0x1804540b5  jz      loc_18045413C
0x1804540bb  test    rdi, rdi
0x1804540be  jz      short loc_18045413C
0x1804540c0  mov     rcx, r15; String
0x1804540c3  lea     r8, [rbp+0AF00h+Context]; Context
0x1804540c7  mov     rdx, cs:off_1836E2140; Delimiter
0x1804540ce  call    strtok_s_0
0x1804540d3  test    rax, rax
0x1804540d6  jz      short loc_18045413C
0x1804540d8  mov     r10, rsp
0x1804540db  mov     rcx, rdi
0x1804540de  mov     rdx, r12
0x1804540e1  lea     r8, aSS_0; "%s/%s"
0x1804540e8  mov     r9, rax
0x1804540eb  mov     [r10+20h], rbx
0x1804540ef  call    mkl_serv_sprintf_s
0x1804540f4  mov     rcx, rdi; FileName
0x1804540f7  lea     rdx, [rbp+0AF00h+Stat]; Stat
0x1804540fe  call    _stat64i32_0
0x180454103  test    eax, eax
0x180454105  jnz     short loc_180454125
0x180454107  movzx   r9d, [rbp+0AF00h+Stat.st_mode]
0x18045410f  test    r9d, 8000h
0x180454116  jz      short loc_180454125
0x180454118  mov     rcx, rdi; Source
0x18045411b  call    _strdup_0
0x180454120  mov     r13, rax
0x180454123  jmp     short loc_18045413C
0x180454125  xor     ecx, ecx; String
0x180454127  lea     r8, [rbp+0AF00h+Context]; Context
0x18045412b  mov     rdx, cs:off_1836E2140; Delimiter
0x180454132  call    strtok_s_0
0x180454137  test    rax, rax
0x18045413a  jnz     short loc_1804540D8
0x18045413c  mov     rcx, rdi; Block
0x18045413f  call    free_0
0x180454144  mov     rcx, r15; Block
0x180454147  call    free_0
0x18045414c  lea     rcx, aMklroot; "MKLROOT"
0x180454153  lea     rdx, [rbp+0AF00h+Source]
0x18045415a  mov     r8d, 1000h
0x180454160  call    mkl_serv_getenv
0x180454165  test    r13, r13
0x180454168  jz      loc_180454343
0x18045416e  test    r13, r13
0x180454171  jz      short loc_1804541C8
0x180454173  mov     cs:mkl_ueaa_device, 0
0x18045417d  call    mkl_ueaa_prv_read_env
0x180454182  nop
0x180454183  mov     cs:mkl_ueaa_devices, eax
0x180454189  xor     edi, edi
0x18045418b  mov     r12, cs:sizeof_be_device_t
0x180454192  mov     ebx, 1
0x180454197  mov     [rbp+0AF00h+var_AEF0], esi
0x18045419a  mov     [rbp+0AF00h+var_AEE8], r14
0x18045419e  lea     rsi, cs:180000000h
0x1804541a5  cmp     dword ptr (rva mkl_ueaa_device_mask+4)[rsi+rdi*4], 0
0x1804541ad  jnz     short loc_180454216
0x1804541af  inc     rdi
0x1804541b2  cmp     rdi, 20h ; ' '
0x1804541b6  jl      short loc_18045419E
0x1804541b8  mov     r14, [rbp+0AF00h+var_AEE8]
0x1804541bc  xor     esi, esi
0x1804541be  mov     cs:mkl_ueaa_initialized, 1
0x1804541c8  mov     rcx, r13; Block
0x1804541cb  call    free_0
0x1804541d0  test    esi, esi
0x1804541d2  jz      short loc_1804541F3
0x1804541d4  mov     ebx, 1
0x1804541d9  cmp     cs:mkl_ueaa_devices, 1
0x1804541e0  jle     short loc_1804541F3
0x1804541e2  mov     ecx, ebx
0x1804541e4  call    mkl_be_device_fini
0x1804541e9  inc     ebx
0x1804541eb  cmp     ebx, cs:mkl_ueaa_devices
0x1804541f1  jl      short loc_1804541E2
0x1804541f3  mov     rcx, [rbp+0AF00h+var_38]
0x1804541fa  xor     rcx, rbp; StackCookie
0x1804541fd  call    __security_check_cookie
0x180454202  mov     eax, esi
0x180454204  lea     rsp, [rbp+0AED0h]
0x18045420b  pop     r15
0x18045420d  pop     r13
0x18045420f  pop     r12
0x180454211  pop     rdi
0x180454212  pop     rsi
0x180454213  pop     rbx
0x180454214  pop     rbp
0x180454215  retn
0x180454216  mov     rax, r12
0x180454219  mov     r14d, 0FFFFFFFFh
0x18045421f  mov     esi, cs:mkl_ueaa_devices
0x180454225  add     rax, 0Fh
0x180454229  and     rax, 0FFFFFFFFFFFFFFF0h
0x18045422d  call    _alloca_probe
0x180454232  sub     rsp, rax
0x180454235  lea     rax, [rsp+0AF30h+Context]
0x18045423a  mov     r15, rax
0x18045423d  call    mkl_serv_default_progress
0x180454242  test    eax, eax
0x180454244  lea     r10, aMicLdLibraryPa; "MIC_LD_LIBRARY_PATH"
0x18045424b  lea     rcx, aLdLibraryPath; "LD_LIBRARY_PATH"
0x180454252  lea     rdx, [rbp+0AF00h+var_2098]
0x180454259  cmovz   rcx, r10
0x18045425d  mov     r8d, 1000h
0x180454263  call    mkl_serv_getenv
0x180454268  mov     rcx, r15
0x18045426b  mov     edx, edi
0x18045426d  mov     r8, r13
0x180454270  lea     r9, [rbp+0AF00h+var_2098]
0x180454277  call    mkl_be_device_init
0x18045427c  test    eax, eax
0x18045427e  jnz     loc_18045431A
0x180454284  mov     rcx, r15
0x180454287  mov     edx, ebx
0x180454289  call    mkl_be_fill_externs_from_device_struct
0x18045428e  mov     [rbp+0AF00h+var_AEE0], 6
0x180454295  mov     [rbp+0AF00h+var_AEDC], ebx
0x180454298  mov     [rbp+0AF00h+var_AED8], esi
0x18045429b  mov     [rbp+0AF00h+var_AED4], 0
0x18045429f  call    mkl_serv_default_progress
0x1804542a4  test    eax, eax
0x1804542a6  lea     rcx, aLdLibraryPath; "LD_LIBRARY_PATH"
0x1804542ad  lea     rsi, aMicLdLibraryPa; "MIC_LD_LIBRARY_PATH"
0x1804542b4  lea     rdx, [rbp+0AF00h+var_3098]
0x1804542bb  cmovz   rcx, rsi
0x1804542bf  mov     r8d, 1000h
0x1804542c5  call    mkl_serv_getenv
0x1804542ca  test    eax, eax
0x1804542cc  jle     short loc_18045431A
0x1804542ce  movsxd  r9, eax
0x1804542d1  lea     rcx, [rbp+0AF00h+var_AED4]
0x1804542d5  mov     edx, 1000h
0x1804542da  lea     r8, [rbp+0AF00h+var_3098]
0x1804542e1  call    mkl_serv_strncpy_s
0x1804542e6  test    eax, eax
0x1804542e8  jnz     short loc_18045431A
0x1804542ea  xor     edx, edx
0x1804542ec  lea     rcx, [rbp+0AF00h+var_AEE0]
0x1804542f0  xor     r8d, r8d
0x1804542f3  mov     r9d, ebx
0x1804542f6  call    mkl_ueaa_prv_invoke_task
0x1804542fb  test    eax, eax
0x1804542fd  jnz     short loc_18045431A
0x1804542ff  mov     ecx, ebx
0x180454301  mov     edx, 1
0x180454306  call    mkl_ueaa_prv_sync_task
0x18045430b  mov     r14d, eax
0x18045430e  mov     esi, 0FFFFFFFFh
0x180454313  test    r14d, r14d
0x180454316  cmovnz  r14d, esi
0x18045431a  mov     rdx, r15
0x18045431d  mov     rax, r12
0x180454320  add     rax, 0Fh
0x180454324  and     rax, 0FFFFFFFFFFFFFFF0h
0x180454328  add     rsp, rax
0x18045432b  test    r14d, r14d
0x18045432e  jnz     short loc_180454337
0x180454330  inc     ebx
0x180454332  jmp     loc_1804541AF
0x180454337  mov     esi, [rbp+0AF00h+var_AEF0]
0x18045433a  mov     r14, [rbp+0AF00h+var_AEE8]
0x18045433e  jmp     loc_1804541C8
0x180454343  xor     r13d, r13d
0x180454346  lea     rcx, [rbp+0AF00h+Source]; Source
0x18045434d  call    _strdup_0
0x180454352  mov     r12, rax
0x180454355  mov     edx, 104h
0x18045435a  lea     rcx, [rbp+0AF00h+Source]
0x180454361  call    mkl_serv_strnlen_s
0x180454366  mov     rdi, rax
0x180454369  mov     rcx, rbx
0x18045436c  mov     edx, 104h
0x180454371  call    mkl_serv_strnlen_s
0x180454376  lea     rdi, [rdi+rax+2]
0x18045437b  mov     rcx, rdi; Size
0x18045437e  call    malloc_0
0x180454383  mov     r15, rax
0x180454386  test    r12, r12
0x180454389  jz      loc_180454410
0x18045438f  test    r15, r15
0x180454392  jz      short loc_180454410
0x180454394  mov     rcx, r12; String
0x180454397  lea     r8, [rbp+0AF00h+var_AEF8]; Context
0x18045439b  mov     rdx, cs:off_1836E2140; Delimiter
0x1804543a2  call    strtok_s_0
0x1804543a7  test    rax, rax
0x1804543aa  jz      short loc_180454410
0x1804543ac  mov     r10, rsp
0x1804543af  mov     rcx, r15
0x1804543b2  mov     rdx, rdi
0x1804543b5  lea     r8, aSS_0; "%s/%s"
0x1804543bc  mov     r9, rax
0x1804543bf  mov     [r10+20h], rbx
0x1804543c3  call    mkl_serv_sprintf_s
0x1804543c8  mov     rcx, r15; FileName
0x1804543cb  lea     rdx, [rbp+0AF00h+var_68]; Stat
0x1804543d2  call    _stat64i32_0
0x1804543d7  test    eax, eax
0x1804543d9  jnz     short loc_1804543F9
0x1804543db  movzx   r9d, [rbp+0AF00h+var_68.st_mode]
0x1804543e3  test    r9d, 8000h
0x1804543ea  jz      short loc_1804543F9
0x1804543ec  mov     rcx, r15; Source
0x1804543ef  call    _strdup_0
0x1804543f4  mov     r13, rax
0x1804543f7  jmp     short loc_180454410
0x1804543f9  xor     ecx, ecx; String
0x1804543fb  lea     r8, [rbp+0AF00h+var_AEF8]; Context
0x1804543ff  mov     rdx, cs:off_1836E2140; Delimiter
0x180454406  call    strtok_s_0
0x18045440b  test    rax, rax
0x18045440e  jnz     short loc_1804543AC
0x180454410  mov     rcx, r15; Block
0x180454413  call    free_0
0x180454418  mov     rcx, r12; Block
0x18045441b  call    free_0
0x180454420  nop
0x180454421  jmp     loc_18045416E
0x180454426  mov     rcx, rbx; Source
0x180454429  call    _strdup_0
0x18045442e  mov     r13, rax
0x180454431  jmp     loc_18045416E
```

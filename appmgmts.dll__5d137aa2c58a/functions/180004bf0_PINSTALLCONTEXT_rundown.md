# PINSTALLCONTEXT_rundown

- ea: `0x180004bf0`
- end: `0x180004d54`
- name: `PINSTALLCONTEXT_rundown`
- size: `356`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180004780`

## callees

- `0x1800016d0`
- `0x1800016f4`
- `0x180002024`
- `0x180004bf0`
- `0x180004fc0`
- `0x18000e69c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004cef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004d11`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004cef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004d11`

## pseudocode

```c
void __fastcall PINSTALLCONTEXT_rundown(void *a1)
{
  __int64 v1; // rsi
  bool v3; // cf
  __int64 v4; // rax
  void *v5; // rdi
  void *v6; // rdi
  HMODULE *v7; // rdi
  HMODULE *v8; // rdi
  __int64 v9; // [rsp+20h] [rbp-238h] BYREF
  int v10; // [rsp+28h] [rbp-230h]
  _DWORD v11[2]; // [rsp+30h] [rbp-228h] BYREF
  __int64 v12; // [rsp+38h] [rbp-220h]
  __int16 v13; // [rsp+40h] [rbp-218h]
  _BYTE v14[510]; // [rsp+42h] [rbp-216h] BYREF

  if ( a1 )
  {
    v1 = *((_QWORD *)a1 + 6);
    if ( v1 )
    {
      memset_0(v14, 0, sizeof(v14));
      v11[0] = 103;
      v9 = 0;
      v10 = 0;
      v3 = *((_BYTE *)a1 + 40) != 0;
      v12 = v1;
      v13 = 0;
      v11[1] = v3 ? 0 : 0xD;
      ((void (__fastcall *)(_DWORD *, __int64 *))gpfnSRSetRetorePointW)(v11, &v9);
    }
    v4 = *((_QWORD *)a1 + 1);
    if ( v4 && !*((_BYTE *)a1 + 40) && !*(_DWORD *)(v4 + 232) )
      *(_DWORD *)(v4 + 232) = 8;
    v5 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      CManagedAppProcessor::~CManagedAppProcessor(*(CManagedAppProcessor **)a1);
      operator delete(v5);
    }
    v6 = (void *)*((_QWORD *)a1 + 1);
    if ( v6 )
    {
      CAppInfo::~CAppInfo(*((CAppInfo **)a1 + 1));
      operator delete(v6);
    }
    v7 = (HMODULE *)*((_QWORD *)a1 + 3);
    if ( v7 )
    {
      if ( *v7 )
        FreeLibrary(*v7);
      operator delete(v7);
    }
    v8 = (HMODULE *)*((_QWORD *)a1 + 4);
    if ( v8 )
    {
      if ( *v8 )
        FreeLibrary(*v8);
      operator delete(v8);
    }
    operator delete(a1);
  }
}

```

## disassembly

```asm
0x180004bf0  test    rcx, rcx
0x180004bf3  jz      locret_180004D53
0x180004bf9  mov     [rsp+arg_8], rbx
0x180004bfe  mov     [rsp+arg_10], rsi
0x180004c03  push    rdi
0x180004c04  sub     rsp, 250h
0x180004c0b  mov     rax, cs:__security_cookie
0x180004c12  xor     rax, rsp
0x180004c15  mov     [rsp+258h+var_18], rax
0x180004c1d  mov     rsi, [rcx+30h]
0x180004c21  mov     rbx, rcx
0x180004c24  test    rsi, rsi
0x180004c27  jz      short loc_180004C80
0x180004c29  xor     edx, edx; Val
0x180004c2b  lea     rcx, [rsp+258h+var_216]; void *
0x180004c30  mov     r8d, 1FEh; Size
0x180004c36  call    memset_0
0x180004c3b  xor     eax, eax
0x180004c3d  mov     [rsp+258h+var_228], 67h ; 'g'
0x180004c45  mov     [rsp+258h+var_238], rax
0x180004c4a  lea     rdx, [rsp+258h+var_238]
0x180004c4f  mov     [rsp+258h+var_230], eax
0x180004c53  mov     al, [rbx+28h]
0x180004c56  neg     al
0x180004c58  mov     [rsp+258h+var_220], rsi
0x180004c5d  sbb     ecx, ecx
0x180004c5f  xor     eax, eax
0x180004c61  not     ecx
0x180004c63  mov     [rsp+258h+var_218], ax
0x180004c68  mov     rax, cs:?gpfnSRSetRetorePointW@@3P6AHPEAU_RESTOREPTINFOW@@PEAU_SMGRSTATUS@@@ZEA; int (*gpfnSRSetRetorePointW)(_RESTOREPTINFOW *,_SMGRSTATUS *)
0x180004c6f  and     ecx, 0Dh
0x180004c72  mov     [rsp+258h+var_224], ecx
0x180004c76  lea     rcx, [rsp+258h+var_228]
0x180004c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c80  mov     rax, [rbx+8]
0x180004c84  mov     esi, 8
0x180004c89  test    rax, rax
0x180004c8c  jz      short loc_180004CA3
0x180004c8e  cmp     byte ptr [rbx+28h], 0
0x180004c92  jnz     short loc_180004CA3
0x180004c94  cmp     dword ptr [rax+0E8h], 0
0x180004c9b  jnz     short loc_180004CA3
0x180004c9d  mov     [rax+0E8h], esi
0x180004ca3  mov     rdi, [rbx]
0x180004ca6  test    rdi, rdi
0x180004ca9  jz      short loc_180004CC0
0x180004cab  mov     rcx, rdi; this
0x180004cae  call    ??1CManagedAppProcessor@@QEAA@XZ; CManagedAppProcessor::~CManagedAppProcessor(void)
0x180004cb3  mov     edx, 1F0h; unsigned __int64
0x180004cb8  mov     rcx, rdi; void *
0x180004cbb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004cc0  mov     rdi, [rbx+8]
0x180004cc4  test    rdi, rdi
0x180004cc7  jz      short loc_180004CDE
0x180004cc9  mov     rcx, rdi; this
0x180004ccc  call    ??1CAppInfo@@QEAA@XZ; CAppInfo::~CAppInfo(void)
0x180004cd1  mov     edx, 1C8h; unsigned __int64
0x180004cd6  mov     rcx, rdi; void *
0x180004cd9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004cde  mov     rdi, [rbx+18h]
0x180004ce2  test    rdi, rdi
0x180004ce5  jz      short loc_180004D00
0x180004ce7  mov     rcx, [rdi]; hLibModule
0x180004cea  test    rcx, rcx
0x180004ced  jz      short loc_180004CF5
0x180004cef  call    cs:__imp_FreeLibrary
0x180004cf5  mov     rdx, rsi; unsigned __int64
0x180004cf8  mov     rcx, rdi; void *
0x180004cfb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004d00  mov     rdi, [rbx+20h]
0x180004d04  test    rdi, rdi
0x180004d07  jz      short loc_180004D22
0x180004d09  mov     rcx, [rdi]; hLibModule
0x180004d0c  test    rcx, rcx
0x180004d0f  jz      short loc_180004D17
0x180004d11  call    cs:__imp_FreeLibrary
0x180004d17  mov     rdx, rsi; unsigned __int64
0x180004d1a  mov     rcx, rdi; void *
0x180004d1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004d22  mov     edx, 38h ; '8'; unsigned __int64
0x180004d27  mov     rcx, rbx; void *
0x180004d2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004d2f  mov     rcx, [rsp+258h+var_18]
0x180004d37  xor     rcx, rsp; StackCookie
0x180004d3a  call    __security_check_cookie
0x180004d3f  lea     r11, [rsp+258h+var_8]
0x180004d47  mov     rbx, [r11+18h]
0x180004d4b  mov     rsi, [r11+20h]
0x180004d4f  mov     rsp, r11
0x180004d52  pop     rdi
0x180004d53  retn
```

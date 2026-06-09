# mkl_ueaa_prv_load_backend_lib

- ea: `0x1804812f0`
- end: `0x1804815d0`
- name: `mkl_ueaa_prv_load_backend_lib`
- size: `736`
- prototype: `__int64 __fastcall(LPCSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180481030`

## callees

- `0x180481130`
- `0x1804812f0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180481348`
- `KERNEL32!GetProcAddress` at `0x180481368`
- `KERNEL32!GetProcAddress` at `0x180481388`
- `KERNEL32!GetProcAddress` at `0x1804813a8`
- `KERNEL32!GetProcAddress` at `0x1804813c8`
- `KERNEL32!GetProcAddress` at `0x1804813e8`
- `KERNEL32!GetProcAddress` at `0x180481408`
- `KERNEL32!GetProcAddress` at `0x180481428`
- `KERNEL32!GetProcAddress` at `0x180481448`
- `KERNEL32!GetProcAddress` at `0x180481468`
- `KERNEL32!GetProcAddress` at `0x180481488`
- `KERNEL32!GetProcAddress` at `0x1804814a8`
- `KERNEL32!GetProcAddress` at `0x1804814c8`
- `KERNEL32!GetProcAddress` at `0x1804814e8`
- `KERNEL32!GetProcAddress` at `0x180481508`
- `KERNEL32!GetProcAddress` at `0x180481528`
- `KERNEL32!GetProcAddress` at `0x180481544`
- `KERNEL32!GetProcAddress` at `0x180481560`
- `KERNEL32!GetProcAddress` at `0x18048157c`
- `KERNEL32!GetProcAddress` at `0x180481598`
- `KERNEL32!GetProcAddress` at `0x180481348`
- `KERNEL32!GetProcAddress` at `0x180481368`
- `KERNEL32!GetProcAddress` at `0x180481388`
- `KERNEL32!GetProcAddress` at `0x1804813a8`
- `KERNEL32!GetProcAddress` at `0x1804813c8`
- `KERNEL32!GetProcAddress` at `0x1804813e8`
- `KERNEL32!GetProcAddress` at `0x180481408`
- `KERNEL32!GetProcAddress` at `0x180481428`
- `KERNEL32!GetProcAddress` at `0x180481448`
- `KERNEL32!GetProcAddress` at `0x180481468`
- `KERNEL32!GetProcAddress` at `0x180481488`
- `KERNEL32!GetProcAddress` at `0x1804814a8`
- `KERNEL32!GetProcAddress` at `0x1804814c8`
- `KERNEL32!GetProcAddress` at `0x1804814e8`
- `KERNEL32!GetProcAddress` at `0x180481508`
- `KERNEL32!GetProcAddress` at `0x180481528`
- `KERNEL32!GetProcAddress` at `0x180481544`
- `KERNEL32!GetProcAddress` at `0x180481560`
- `KERNEL32!GetProcAddress` at `0x18048157c`
- `KERNEL32!GetProcAddress` at `0x180481598`
- `KERNEL32!LoadLibraryExA` at `0x18048132c`
- `KERNEL32!LoadLibraryExA` at `0x18048132c`

## string_xrefs

- `0x1804813c1`: `COIProcessCreateFromFile`
- `0x180481481`: `COIBufferWrite`
- `0x1804814c1`: `COIBufferRead`
- `0x180481521`: `COIBufferCreate`
- `0x18048153d`: `COIBufferCopy`
- `0x180481559`: `COIPipelineCreate`
- `0x180481575`: `COIBufferCreateFromMemory`

## pseudocode

```c
__int64 __fastcall mkl_ueaa_prv_load_backend_lib(LPCSTR lpLibFileName)
{
  unsigned int v2; // esi
  __int64 result; // rax
  HMODULE Library; // rax
  HMODULE v5; // rdi

  v2 = -1;
  if ( dword_18371F830 )
  {
    result = 0;
    if ( dword_18371F830 != 1 )
      return 0xFFFFFFFFLL;
  }
  else
  {
    if ( (unsigned int)mkl_serv_default_progress() )
      goto LABEL_28;
    Library = LoadLibraryExA(lpLibFileName, 0, 0);
    v5 = Library;
    if ( !Library )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIEventRegisterUserEvent = (__int64)GetProcAddress(Library, "COIEventRegisterUserEvent");
    if ( !mkl_ueaa_prv_fp_COIEventRegisterUserEvent )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIPipelineDestroy = (__int64)GetProcAddress(v5, "COIPipelineDestroy");
    if ( !mkl_ueaa_prv_fp_COIPipelineDestroy )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIEngineGetInfo = (__int64)GetProcAddress(v5, "COIEngineGetInfo");
    if ( !mkl_ueaa_prv_fp_COIEngineGetInfo )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIProcessDestroy = (__int64)GetProcAddress(v5, "COIProcessDestroy");
    if ( !mkl_ueaa_prv_fp_COIProcessDestroy )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIProcessCreateFromFile = (__int64)GetProcAddress(v5, "COIProcessCreateFromFile");
    if ( !mkl_ueaa_prv_fp_COIProcessCreateFromFile )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIEventUnregisterUserEvent = (__int64)GetProcAddress(v5, "COIEventUnregisterUserEvent");
    if ( !mkl_ueaa_prv_fp_COIEventUnregisterUserEvent )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIEventWait = (__int64)GetProcAddress(v5, "COIEventWait");
    if ( !mkl_ueaa_prv_fp_COIEventWait )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIBufferSetState = (__int64)GetProcAddress(v5, "COIBufferSetState");
    if ( !mkl_ueaa_prv_fp_COIBufferSetState )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIProcessGetFunctionHandles = (__int64)GetProcAddress(v5, "COIProcessGetFunctionHandles");
    if ( !mkl_ueaa_prv_fp_COIProcessGetFunctionHandles )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIBufferDestroy = (__int64)GetProcAddress(v5, "COIBufferDestroy");
    if ( !mkl_ueaa_prv_fp_COIBufferDestroy )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIBufferWrite = (__int64)GetProcAddress(v5, "COIBufferWrite");
    if ( !mkl_ueaa_prv_fp_COIBufferWrite )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIEngineGetCount = (__int64)GetProcAddress(v5, "COIEngineGetCount");
    if ( !mkl_ueaa_prv_fp_COIEngineGetCount )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIBufferRead = (__int64)GetProcAddress(v5, "COIBufferRead");
    if ( !mkl_ueaa_prv_fp_COIBufferRead )
      goto LABEL_28;
    mkl_ueaa_prv_fp_COIPipelineRunFunction = (__int64)GetProcAddress(v5, "COIPipelineRunFunction");
    if ( mkl_ueaa_prv_fp_COIPipelineRunFunction
      && (mkl_ueaa_prv_fp_COIResultGetName = (__int64)GetProcAddress(v5, "COIResultGetName")) != 0
      && (mkl_ueaa_prv_fp_COIBufferCreate = (__int64)GetProcAddress(v5, "COIBufferCreate")) != 0
      && (mkl_ueaa_prv_fp_COIBufferCopy = (__int64)GetProcAddress(v5, "COIBufferCopy")) != 0
      && (mkl_ueaa_prv_fp_COIPipelineCreate = (__int64)GetProcAddress(v5, "COIPipelineCreate")) != 0
      && (mkl_ueaa_prv_fp_COIBufferCreateFromMemory = (__int64)GetProcAddress(v5, "COIBufferCreateFromMemory")) != 0
      && (mkl_ueaa_prv_fp_COIEngineGetHandle = (__int64)GetProcAddress(v5, "COIEngineGetHandle")) != 0 )
    {
      dword_18371F830 = 1;
      return 0;
    }
    else
    {
LABEL_28:
      dword_18371F830 = -1;
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x1804812f0  push    rsi
0x1804812f1  push    rdi
0x1804812f2  sub     rsp, 28h
0x1804812f6  mov     rdi, rcx
0x1804812f9  mov     edx, cs:dword_18371F830
0x1804812ff  mov     esi, 0FFFFFFFFh
0x180481304  test    edx, edx
0x180481306  jz      short loc_180481317
0x180481308  xor     eax, eax
0x18048130a  cmp     edx, 1
0x18048130d  cmovnz  eax, esi
0x180481310  add     rsp, 28h
0x180481314  pop     rdi
0x180481315  pop     rsi
0x180481316  retn
0x180481317  call    mkl_serv_default_progress
0x18048131c  test    eax, eax
0x18048131e  jnz     loc_1804815B8
0x180481324  mov     rcx, rdi; lpLibFileName
0x180481327  xor     edx, edx; hFile
0x180481329  xor     r8d, r8d; dwFlags
0x18048132c  call    cs:__imp_LoadLibraryExA
0x180481332  mov     rdi, rax
0x180481335  test    rdi, rdi
0x180481338  jz      loc_1804815B8
0x18048133e  mov     rcx, rdi; hModule
0x180481341  lea     rdx, aCoieventregist; "COIEventRegisterUserEvent"
0x180481348  call    cs:__imp_GetProcAddress
0x18048134e  mov     cs:mkl_ueaa_prv_fp_COIEventRegisterUserEvent, rax
0x180481355  test    rax, rax
0x180481358  jz      loc_1804815B8
0x18048135e  mov     rcx, rdi; hModule
0x180481361  lea     rdx, aCoipipelinedes; "COIPipelineDestroy"
0x180481368  call    cs:__imp_GetProcAddress
0x18048136e  mov     cs:mkl_ueaa_prv_fp_COIPipelineDestroy, rax
0x180481375  test    rax, rax
0x180481378  jz      loc_1804815B8
0x18048137e  mov     rcx, rdi; hModule
0x180481381  lea     rdx, aCoienginegetin; "COIEngineGetInfo"
0x180481388  call    cs:__imp_GetProcAddress
0x18048138e  mov     cs:mkl_ueaa_prv_fp_COIEngineGetInfo, rax
0x180481395  test    rax, rax
0x180481398  jz      loc_1804815B8
0x18048139e  mov     rcx, rdi; hModule
0x1804813a1  lea     rdx, aCoiprocessdest; "COIProcessDestroy"
0x1804813a8  call    cs:__imp_GetProcAddress
0x1804813ae  mov     cs:mkl_ueaa_prv_fp_COIProcessDestroy, rax
0x1804813b5  test    rax, rax
0x1804813b8  jz      loc_1804815B8
0x1804813be  mov     rcx, rdi; hModule
0x1804813c1  lea     rdx, aCoiprocesscrea; "COIProcessCreateFromFile"
0x1804813c8  call    cs:__imp_GetProcAddress
0x1804813ce  mov     cs:mkl_ueaa_prv_fp_COIProcessCreateFromFile, rax
0x1804813d5  test    rax, rax
0x1804813d8  jz      loc_1804815B8
0x1804813de  mov     rcx, rdi; hModule
0x1804813e1  lea     rdx, aCoieventunregi; "COIEventUnregisterUserEvent"
0x1804813e8  call    cs:__imp_GetProcAddress
0x1804813ee  mov     cs:mkl_ueaa_prv_fp_COIEventUnregisterUserEvent, rax
0x1804813f5  test    rax, rax
0x1804813f8  jz      loc_1804815B8
0x1804813fe  mov     rcx, rdi; hModule
0x180481401  lea     rdx, aCoieventwait; "COIEventWait"
0x180481408  call    cs:__imp_GetProcAddress
0x18048140e  mov     cs:mkl_ueaa_prv_fp_COIEventWait, rax
0x180481415  test    rax, rax
0x180481418  jz      loc_1804815B8
0x18048141e  mov     rcx, rdi; hModule
0x180481421  lea     rdx, aCoibuffersetst; "COIBufferSetState"
0x180481428  call    cs:__imp_GetProcAddress
0x18048142e  mov     cs:mkl_ueaa_prv_fp_COIBufferSetState, rax
0x180481435  test    rax, rax
0x180481438  jz      loc_1804815B8
0x18048143e  mov     rcx, rdi; hModule
0x180481441  lea     rdx, aCoiprocessgetf; "COIProcessGetFunctionHandles"
0x180481448  call    cs:__imp_GetProcAddress
0x18048144e  mov     cs:mkl_ueaa_prv_fp_COIProcessGetFunctionHandles, rax
0x180481455  test    rax, rax
0x180481458  jz      loc_1804815B8
0x18048145e  mov     rcx, rdi; hModule
0x180481461  lea     rdx, aCoibufferdestr; "COIBufferDestroy"
0x180481468  call    cs:__imp_GetProcAddress
0x18048146e  mov     cs:mkl_ueaa_prv_fp_COIBufferDestroy, rax
0x180481475  test    rax, rax
0x180481478  jz      loc_1804815B8
0x18048147e  mov     rcx, rdi; hModule
0x180481481  lea     rdx, aCoibufferwrite; "COIBufferWrite"
0x180481488  call    cs:__imp_GetProcAddress
0x18048148e  mov     cs:mkl_ueaa_prv_fp_COIBufferWrite, rax
0x180481495  test    rax, rax
0x180481498  jz      loc_1804815B8
0x18048149e  mov     rcx, rdi; hModule
0x1804814a1  lea     rdx, aCoienginegetco; "COIEngineGetCount"
0x1804814a8  call    cs:__imp_GetProcAddress
0x1804814ae  mov     cs:mkl_ueaa_prv_fp_COIEngineGetCount, rax
0x1804814b5  test    rax, rax
0x1804814b8  jz      loc_1804815B8
0x1804814be  mov     rcx, rdi; hModule
0x1804814c1  lea     rdx, aCoibufferread; "COIBufferRead"
0x1804814c8  call    cs:__imp_GetProcAddress
0x1804814ce  mov     cs:mkl_ueaa_prv_fp_COIBufferRead, rax
0x1804814d5  test    rax, rax
0x1804814d8  jz      loc_1804815B8
0x1804814de  mov     rcx, rdi; hModule
0x1804814e1  lea     rdx, aCoipipelinerun; "COIPipelineRunFunction"
0x1804814e8  call    cs:__imp_GetProcAddress
0x1804814ee  mov     cs:mkl_ueaa_prv_fp_COIPipelineRunFunction, rax
0x1804814f5  test    rax, rax
0x1804814f8  jz      loc_1804815B8
0x1804814fe  mov     rcx, rdi; hModule
0x180481501  lea     rdx, aCoiresultgetna; "COIResultGetName"
0x180481508  call    cs:__imp_GetProcAddress
0x18048150e  mov     cs:mkl_ueaa_prv_fp_COIResultGetName, rax
0x180481515  test    rax, rax
0x180481518  jz      loc_1804815B8
0x18048151e  mov     rcx, rdi; hModule
0x180481521  lea     rdx, aCoibuffercreat; "COIBufferCreate"
0x180481528  call    cs:__imp_GetProcAddress
0x18048152e  mov     cs:mkl_ueaa_prv_fp_COIBufferCreate, rax
0x180481535  test    rax, rax
0x180481538  jz      short loc_1804815B8
0x18048153a  mov     rcx, rdi; hModule
0x18048153d  lea     rdx, aCoibuffercopy; "COIBufferCopy"
0x180481544  call    cs:__imp_GetProcAddress
0x18048154a  mov     cs:mkl_ueaa_prv_fp_COIBufferCopy, rax
0x180481551  test    rax, rax
0x180481554  jz      short loc_1804815B8
0x180481556  mov     rcx, rdi; hModule
0x180481559  lea     rdx, aCoipipelinecre; "COIPipelineCreate"
0x180481560  call    cs:__imp_GetProcAddress
0x180481566  mov     cs:mkl_ueaa_prv_fp_COIPipelineCreate, rax
0x18048156d  test    rax, rax
0x180481570  jz      short loc_1804815B8
0x180481572  mov     rcx, rdi; hModule
0x180481575  lea     rdx, aCoibuffercreat_0; "COIBufferCreateFromMemory"
0x18048157c  call    cs:__imp_GetProcAddress
0x180481582  mov     cs:mkl_ueaa_prv_fp_COIBufferCreateFromMemory, rax
0x180481589  test    rax, rax
0x18048158c  jz      short loc_1804815B8
0x18048158e  mov     rcx, rdi; hModule
0x180481591  lea     rdx, aCoienginegetha; "COIEngineGetHandle"
0x180481598  call    cs:__imp_GetProcAddress
0x18048159e  mov     cs:mkl_ueaa_prv_fp_COIEngineGetHandle, rax
0x1804815a5  test    rax, rax
0x1804815a8  jz      short loc_1804815B8
0x1804815aa  mov     cs:dword_18371F830, 1
0x1804815b4  xor     esi, esi
0x1804815b6  jmp     short loc_1804815C2
0x1804815b8  mov     cs:dword_18371F830, 0FFFFFFFFh
0x1804815c2  mov     eax, esi
0x1804815c4  add     rsp, 28h
0x1804815c8  pop     rdi
0x1804815c9  pop     rsi
0x1804815ca  retn
```

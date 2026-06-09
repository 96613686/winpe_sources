# ElevateCreateProcess_Detect(int *,unsigned __int64,unsigned __int64,_PCA_EVENT_ETW_FROM_DM_PARAM *)

- ea: `0x1800b61a0`
- end: `0x1800b6322`
- name: `?ElevateCreateProcess_Detect@@YAKPEAH_K1PEAU_PCA_EVENT_ETW_FROM_DM_PARAM@@@Z`
- size: `386`
- prototype: `unsigned int(int *, unsigned __int64, unsigned __int64, struct _PCA_EVENT_ETW_FROM_DM_PARAM *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012920`
- `0x180013fac`
- `0x18001b320`
- `0x1800b61a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b62e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b62e0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b623a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b623a`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x1800b6271`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x1800b6271`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x1800b62f0`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x1800b62f0`

## string_xrefs

- `0x1800b624c`: `Ignored,Process not available for manifest check`
- `0x1800b627e`: `Failed to read process data -> ignoring process %d`
- `0x1800b6202`: `Resolver,ElevateCreateProcess`
- `0x1800b6255`: `Resolver,ElevateCreateProcess`
- `0x1800b62cd`: `Resolver,ElevateCreateProcess`
- `0x1800b621e`: `Ignored,SwitchBack manifest detected`
- `0x1800b62c2`: `Ignored,Child process SwitchBack manifest detected`
- `0x1800b628f`: `ElevateCreateProcess_Detect`
- `0x1800b62b0`: `Ignored,Child process UAC manifest detected`
- `0x1800b61f9`: `Ignored,UAC manifest detected`

## pseudocode

```c
__int64 __fastcall ElevateCreateProcess_Detect(
        int *a1,
        int *a2,
        unsigned __int64 a3,
        struct _PCA_EVENT_ETW_FROM_DM_PARAM *a4)
{
  unsigned int v8; // ebp
  struct _PCA_CHAIN *v9; // rax
  unsigned int v10; // r8d
  int v11; // esi
  int v12; // ebx
  HANDLE v13; // rax
  void *v14; // r14
  __int64 result; // rax
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF

  v16 = 0;
  v8 = *((_DWORD *)PcapChainFromHandle(a3) + 4);
  v9 = PcapChainFromHandle(a3);
  v10 = *((_DWORD *)a4 + 7);
  v11 = 1;
  v16 = 0;
  if ( *((_DWORD *)v9 + 1184) )
  {
    PcaTracePrintf("Resolver,ElevateCreateProcess", v8, v10, "Ignored,UAC manifest detected");
LABEL_3:
    v12 = 0;
    goto LABEL_17;
  }
  if ( *((_DWORD *)v9 + 1183) )
  {
    PcaTracePrintf("Resolver,ElevateCreateProcess", v8, v10, "Ignored,SwitchBack manifest detected");
    goto LABEL_3;
  }
  v12 = 1;
  if ( *((_DWORD *)v9 + 7) == v10 )
    goto LABEL_19;
  v13 = OpenProcess(0x1FFFFFu, 0, v10);
  v14 = v13;
  if ( !v13 )
  {
    PcaTracePrintf(
      "Resolver,ElevateCreateProcess",
      v8,
      *((_DWORD *)a4 + 7),
      "Ignored,Process not available for manifest check");
    goto LABEL_17;
  }
  if ( !(unsigned int)BaseReadAppCompatDataForProcess(v13, &v16, 0) )
  {
    if ( *(_DWORD *)(v16 + 4440) )
    {
      PcaTracePrintf(
        "Resolver,ElevateCreateProcess",
        v8,
        *((_DWORD *)a4 + 7),
        "Ignored,Child process UAC manifest detected");
    }
    else
    {
      if ( !*(_DWORD *)(v16 + 4436) )
        goto LABEL_16;
      PcaTracePrintf(
        "Resolver,ElevateCreateProcess",
        v8,
        *((_DWORD *)a4 + 7),
        "Ignored,Child process SwitchBack manifest detected");
    }
    v12 = 0;
    goto LABEL_16;
  }
  AslLogCallPrintf(
    2,
    (unsigned int)"ElevateCreateProcess_Detect",
    182,
    (unsigned int)"Failed to read process data -> ignoring process %d",
    *((_DWORD *)a4 + 7));
LABEL_16:
  CloseHandle(v14);
LABEL_17:
  if ( v16 )
    BaseFreeAppCompatDataForProcess();
LABEL_19:
  if ( !*a2 && !v12 )
    v11 = 0;
  result = 0;
  *a2 = v11;
  *a1 = v11;
  return result;
}

```

## disassembly

```asm
0x1800b61a0  mov     [rsp+arg_8], rbx
0x1800b61a5  mov     [rsp+arg_10], rbp
0x1800b61aa  push    rsi
0x1800b61ab  push    rdi
0x1800b61ac  push    r12
0x1800b61ae  push    r14
0x1800b61b0  push    r15
0x1800b61b2  sub     rsp, 30h
0x1800b61b6  mov     r12, rcx
0x1800b61b9  mov     [rsp+58h+arg_0], 0
0x1800b61c2  mov     rcx, r8; unsigned __int64
0x1800b61c5  mov     rdi, r9
0x1800b61c8  mov     rbx, r8
0x1800b61cb  mov     r15, rdx
0x1800b61ce  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800b61d3  mov     rcx, rbx; unsigned __int64
0x1800b61d6  mov     ebp, [rax+10h]
0x1800b61d9  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800b61de  mov     r8d, [rdi+1Ch]; unsigned int
0x1800b61e2  mov     esi, 1
0x1800b61e7  mov     [rsp+58h+arg_0], 0
0x1800b61f0  cmp     dword ptr [rax+1280h], 0
0x1800b61f7  jz      short loc_1800B6215
0x1800b61f9  lea     r9, aIgnoredUacMani; "Ignored,UAC manifest detected"
0x1800b6200  mov     edx, ebp; unsigned int
0x1800b6202  lea     rcx, aResolverElevat; "Resolver,ElevateCreateProcess"
0x1800b6209  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b620e  xor     ebx, ebx
0x1800b6210  jmp     loc_1800B62E6
0x1800b6215  cmp     dword ptr [rax+127Ch], 0
0x1800b621c  jz      short loc_1800B6227
0x1800b621e  lea     r9, aIgnoredSwitchb; "Ignored,SwitchBack manifest detected"
0x1800b6225  jmp     short loc_1800B6200
0x1800b6227  mov     ebx, esi
0x1800b6229  cmp     [rax+1Ch], r8d
0x1800b622d  jz      loc_1800B62F6
0x1800b6233  xor     edx, edx; bInheritHandle
0x1800b6235  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800b623a  call    cs:__imp_OpenProcess
0x1800b6240  mov     r14, rax
0x1800b6243  test    rax, rax
0x1800b6246  jnz     short loc_1800B6266
0x1800b6248  mov     r8d, [rdi+1Ch]; unsigned int
0x1800b624c  lea     r9, aIgnoredProcess; "Ignored,Process not available for manif"...
0x1800b6253  mov     edx, ebp; unsigned int
0x1800b6255  lea     rcx, aResolverElevat; "Resolver,ElevateCreateProcess"
0x1800b625c  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b6261  jmp     loc_1800B62E6
0x1800b6266  xor     r8d, r8d
0x1800b6269  lea     rdx, [rsp+58h+arg_0]
0x1800b626e  mov     rcx, r14
0x1800b6271  call    cs:__imp_BaseReadAppCompatDataForProcess
0x1800b6277  test    eax, eax
0x1800b6279  jz      short loc_1800B62A2
0x1800b627b  mov     eax, [rdi+1Ch]
0x1800b627e  lea     r9, aFailedToReadPr_1; "Failed to read process data -> ignoring"...
0x1800b6285  mov     r8d, 0B6h
0x1800b628b  mov     [rsp+58h+var_38], eax
0x1800b628f  lea     rdx, aElevatecreatep; "ElevateCreateProcess_Detect"
0x1800b6296  mov     ecx, 2
0x1800b629b  call    AslLogCallPrintf
0x1800b62a0  jmp     short loc_1800B62DD
0x1800b62a2  mov     rax, [rsp+58h+arg_0]
0x1800b62a7  cmp     dword ptr [rax+1158h], 0
0x1800b62ae  jz      short loc_1800B62B9
0x1800b62b0  lea     r9, aIgnoredChildPr; "Ignored,Child process UAC manifest dete"...
0x1800b62b7  jmp     short loc_1800B62C9
0x1800b62b9  cmp     dword ptr [rax+1154h], 0
0x1800b62c0  jz      short loc_1800B62DD
0x1800b62c2  lea     r9, aIgnoredChildPr_0; "Ignored,Child process SwitchBack manife"...
0x1800b62c9  mov     r8d, [rdi+1Ch]; unsigned int
0x1800b62cd  lea     rcx, aResolverElevat; "Resolver,ElevateCreateProcess"
0x1800b62d4  mov     edx, ebp; unsigned int
0x1800b62d6  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b62db  xor     ebx, ebx
0x1800b62dd  mov     rcx, r14; hObject
0x1800b62e0  call    cs:__imp_CloseHandle
0x1800b62e6  mov     rcx, [rsp+58h+arg_0]
0x1800b62eb  test    rcx, rcx
0x1800b62ee  jz      short loc_1800B62F6
0x1800b62f0  call    cs:__imp_BaseFreeAppCompatDataForProcess
0x1800b62f6  cmp     dword ptr [r15], 0
0x1800b62fa  jnz     short loc_1800B6302
0x1800b62fc  test    ebx, ebx
0x1800b62fe  jnz     short loc_1800B6302
0x1800b6300  xor     esi, esi
0x1800b6302  mov     rbx, [rsp+58h+arg_8]
0x1800b6307  xor     eax, eax
0x1800b6309  mov     rbp, [rsp+58h+arg_10]
0x1800b630e  mov     [r15], esi
0x1800b6311  mov     [r12], esi
0x1800b6315  add     rsp, 30h
0x1800b6319  pop     r15
0x1800b631b  pop     r14
0x1800b631d  pop     r12
0x1800b631f  pop     rdi
0x1800b6320  pop     rsi
0x1800b6321  retn
```

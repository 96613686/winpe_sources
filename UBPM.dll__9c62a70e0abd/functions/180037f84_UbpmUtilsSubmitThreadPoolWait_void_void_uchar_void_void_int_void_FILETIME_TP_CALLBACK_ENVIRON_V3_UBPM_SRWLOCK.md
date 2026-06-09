# UbpmUtilsSubmitThreadPoolWait(void (*)(void *,uchar,void *),void *,int,void *,_FILETIME *,_TP_CALLBACK_ENVIRON_V3 *,_UBPM_SRWLOCK *)

- ea: `0x180037f84`
- end: `0x180038130`
- name: `?UbpmUtilsSubmitThreadPoolWait@@YAKP6AXPEAXE0@Z0H0PEAU_FILETIME@@PEAU_TP_CALLBACK_ENVIRON_V3@@PEAU_UBPM_SRWLOCK@@@Z`
- size: `428`
- prototype: `unsigned int(void (*)(void *, unsigned __int8, void *), void *, int, void *, struct _FILETIME *, struct _TP_CALLBACK_ENVIRON_V3 *, struct _UBPM_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180036810`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x180028ae8`
- `0x1800351ec`
- `0x180037f84`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180038110`
- `ntdll!RtlReleaseSRWLockShared` at `0x180038110`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003809a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003809a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800380fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800380fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800380ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800380ab`

## pseudocode

```c
__int64 __fastcall UbpmUtilsSubmitThreadPoolWait(
        void (*a1)(void *, unsigned __int8, void *),
        void *a2,
        __int64 a3,
        void *a4)
{
  _DWORD *v6; // rdi
  __int64 v7; // rdx
  DWORD LastError; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rax
  unsigned int v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = 0;
  v6 = UbpmAlloc(0x30u);
  if ( !v6 )
  {
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 32;
LABEL_5:
      WPP_SF_d(v11[2], v12, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  UBPM_TRY_ACQUIRE_SRWLOCK_SHARED((struct _UBPM_SRWLOCK *)&g_TpSubmitLock, &v17);
  LastError = v17;
  if ( !v17 )
  {
    if ( g_pThreadpool )
    {
      ThreadpoolWait = CreateThreadpoolWait(UbpmUtilsWaitCallback, v6, &g_CallbackEnv);
      if ( ThreadpoolWait )
      {
        *((_BYTE *)v6 + 24) |= 1u;
        *((_QWORD *)v6 + 2) = UbpmpRegistryChangeCallback;
        *v6 = 1886667349;
        *((_QWORD *)v6 + 1) = a2;
        v6 = 0;
        SetThreadpoolWait(ThreadpoolWait, a4, 0);
        goto LABEL_20;
      }
      LastError = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v14 = 35;
    }
    else
    {
      LastError = 1115;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v14 = 34;
    }
    WPP_SF_d(v13[2], v14, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
LABEL_20:
    RtlReleaseSRWLockShared(&g_TpSubmitLock);
    goto LABEL_21;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 33;
    goto LABEL_5;
  }
LABEL_21:
  UBPM_MIDL_user_free(v6, v7, v9, v10);
  return LastError;
}

```

## disassembly

```asm
0x180037f84  mov     [rsp+arg_10], r8d
0x180037f89  push    rbx
0x180037f8a  push    rbp
0x180037f8b  push    rsi
0x180037f8c  push    rdi
0x180037f8d  sub     rsp, 28h
0x180037f91  mov     ecx, 30h ; '0'; Size
0x180037f96  mov     [rsp+48h+arg_10], 0
0x180037f9e  mov     rsi, r9
0x180037fa1  mov     rbp, rdx
0x180037fa4  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180037fa9  mov     rdi, rax
0x180037fac  test    rax, rax
0x180037faf  jnz     short loc_180037FFB
0x180037fb1  call    cs:__imp_GetLastError
0x180037fb8  nop     dword ptr [rax+rax+00h]
0x180037fbd  mov     ebx, eax
0x180037fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fc6  lea     rax, WPP_GLOBAL_Control
0x180037fcd  cmp     rcx, rax
0x180037fd0  jz      loc_18003811C
0x180037fd6  test    byte ptr [rcx+1Ch], 1
0x180037fda  jz      loc_18003811C
0x180037fe0  lea     edx, [rdi+20h]
0x180037fe3  mov     rcx, [rcx+10h]
0x180037fe7  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180037fee  mov     r9d, ebx
0x180037ff1  call    WPP_SF_d
0x180037ff6  jmp     loc_18003811C
0x180037ffb  lea     rdx, [rsp+48h+arg_10]; unsigned int *
0x180038000  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x180038007  call    ?UBPM_TRY_ACQUIRE_SRWLOCK_SHARED@@YAXAEAU_UBPM_SRWLOCK@@PEAK@Z; UBPM_TRY_ACQUIRE_SRWLOCK_SHARED(_UBPM_SRWLOCK &,ulong *)
0x18003800c  mov     ebx, [rsp+48h+arg_10]
0x180038010  test    ebx, ebx
0x180038012  jz      short loc_18003803C
0x180038014  mov     rcx, cs:WPP_GLOBAL_Control
0x18003801b  lea     rax, WPP_GLOBAL_Control
0x180038022  cmp     rcx, rax
0x180038025  jz      loc_18003811C
0x18003802b  test    byte ptr [rcx+1Ch], 1
0x18003802f  jz      loc_18003811C
0x180038035  mov     edx, 21h ; '!'
0x18003803a  jmp     short loc_180037FE3
0x18003803c  cmp     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * g_pThreadpool
0x180038044  jnz     short loc_180038089
0x180038046  mov     ebx, 45Bh
0x18003804b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038052  lea     rax, WPP_GLOBAL_Control
0x180038059  cmp     rcx, rax
0x18003805c  jz      loc_180038109
0x180038062  test    byte ptr [rcx+1Ch], 1
0x180038066  jz      loc_180038109
0x18003806c  mov     edx, 22h ; '"'
0x180038071  mov     rcx, [rcx+10h]
0x180038075  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18003807c  mov     r9d, ebx
0x18003807f  call    WPP_SF_d
0x180038084  jmp     loc_180038109
0x180038089  lea     r8, ?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180038090  mov     rdx, rdi; pv
0x180038093  lea     rcx, ?UbpmUtilsWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18003809a  call    cs:__imp_CreateThreadpoolWait
0x1800380a1  nop     dword ptr [rax+rax+00h]
0x1800380a6  test    rax, rax
0x1800380a9  jnz     short loc_1800380D9
0x1800380ab  call    cs:__imp_GetLastError
0x1800380b2  nop     dword ptr [rax+rax+00h]
0x1800380b7  mov     ebx, eax
0x1800380b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380c0  lea     rax, WPP_GLOBAL_Control
0x1800380c7  cmp     rcx, rax
0x1800380ca  jz      short loc_180038109
0x1800380cc  test    byte ptr [rcx+1Ch], 1
0x1800380d0  jz      short loc_180038109
0x1800380d2  mov     edx, 23h ; '#'
0x1800380d7  jmp     short loc_180038071
0x1800380d9  or      byte ptr [rdi+18h], 1
0x1800380dd  lea     rdx, ?UbpmpRegistryChangeCallback@@YAXPEAXE0@Z; UbpmpRegistryChangeCallback(void *,uchar,void *)
0x1800380e4  mov     [rdi+10h], rdx
0x1800380e8  xor     r8d, r8d; pftTimeout
0x1800380eb  mov     dword ptr [rdi], 70744255h
0x1800380f1  mov     rdx, rsi; h
0x1800380f4  mov     [rdi+8], rbp
0x1800380f8  mov     rcx, rax; pwa
0x1800380fb  xor     edi, edi
0x1800380fd  call    cs:__imp_SetThreadpoolWait
0x180038104  nop     dword ptr [rax+rax+00h]
0x180038109  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x180038110  call    cs:__imp_RtlReleaseSRWLockShared
0x180038117  nop     dword ptr [rax+rax+00h]
0x18003811c  mov     rcx, rdi
0x18003811f  call    UBPM_MIDL_user_free
0x180038124  mov     eax, ebx
0x180038126  add     rsp, 28h
0x18003812a  pop     rdi
0x18003812b  pop     rsi
0x18003812c  pop     rbp
0x18003812d  pop     rbx
0x18003812e  retn
```

# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180026668`
- end: `0x180026816`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `430`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800265f0`

## callees

- `0x18000ab60`
- `0x18000c610`
- `0x180015c10`
- `0x180016a40`
- `0x180017676`
- `0x180023a64`
- `0x180024c5c`
- `0x180025f88`
- `0x180026668`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800266d1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026768`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800266d1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026768`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError_0() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180026668  mov     [rsp-8+arg_8], rbx
0x18002666d  push    rbp
0x18002666e  push    rdi
0x18002666f  push    r14
0x180026671  lea     rbp, [rsp-160h]
0x180026679  sub     rsp, 260h
0x180026680  mov     rax, cs:__security_cookie
0x180026687  xor     rax, rsp
0x18002668a  mov     [rbp+170h+var_20], rax
0x180026691  mov     rdi, r8
0x180026694  mov     qword ptr [r8], 0
0x18002669b  mov     r8, rcx; unsigned __int16 *
0x18002669e  mov     r14d, 104h
0x1800266a4  mov     edx, r14d; unsigned __int64
0x1800266a7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800266ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800266b1  lea     r8, aP0; "_p0"
0x1800266b8  mov     edx, r14d; unsigned __int64
0x1800266bb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800266c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800266c5  lea     r8, [rsp+270h+Name]; lpName
0x1800266ca  xor     edx, edx; bInheritHandle
0x1800266cc  mov     ecx, 1F0003h; dwDesiredAccess
0x1800266d1  call    cs:__imp_OpenSemaphoreW
0x1800266d8  nop     dword ptr [rax+rax+00h]
0x1800266dd  mov     [rsp+270h+var_240], rax
0x1800266e2  test    rax, rax
0x1800266e5  jnz     short loc_18002670C
0x1800266e7  call    GetLastError_0
0x1800266ec  cmp     eax, 2
0x1800266ef  jz      loc_1800267E4
0x1800266f5  mov     rcx, [rbp+178h]; this
0x1800266fc  lea     edx, [r14-34h]; void *
0x180026700  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026705  mov     ebx, eax
0x180026707  jmp     loc_1800267E6
0x18002670c  lea     rdx, [rsp+270h+var_24C]; int *
0x180026711  mov     [rsp+270h+var_24C], 0
0x180026719  mov     rcx, rax; hHandle
0x18002671c  mov     [rsp+270h+var_250], 0; int
0x180026724  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026729  mov     ebx, eax
0x18002672b  test    eax, eax
0x18002672d  jns     short loc_180026748
0x18002672f  mov     rcx, [rbp+178h]; this
0x180026736  mov     r9d, eax; char *
0x180026739  mov     edx, 0D6h; void *
0x18002673e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026743  jmp     loc_1800267E6
0x180026748  lea     r8, asc_180092E98; "h"
0x18002674f  mov     rdx, r14; unsigned __int64
0x180026752  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026757  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002675c  lea     r8, [rsp+270h+Name]; lpName
0x180026761  xor     edx, edx; bInheritHandle
0x180026763  mov     ecx, 1F0003h; dwDesiredAccess
0x180026768  call    cs:__imp_OpenSemaphoreW
0x18002676f  nop     dword ptr [rax+rax+00h]
0x180026774  mov     [rsp+270h+var_248], rax
0x180026779  test    rax, rax
0x18002677c  jnz     short loc_18002679D
0x18002677e  mov     rcx, [rbp+178h]; this
0x180026785  mov     edx, 0DCh; void *
0x18002678a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002678f  mov     ebx, eax
0x180026791  lea     rcx, [rsp+270h+var_248]
0x180026796  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002679b  jmp     short loc_1800267E6
0x18002679d  lea     rdx, [rsp+270h+var_250]; int *
0x1800267a2  mov     rcx, rax; hHandle
0x1800267a5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800267aa  mov     ebx, eax
0x1800267ac  test    eax, eax
0x1800267ae  jns     short loc_1800267C6
0x1800267b0  mov     rcx, [rbp+178h]; this
0x1800267b7  mov     r9d, eax; char *
0x1800267ba  mov     edx, 0DEh; void *
0x1800267bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800267c4  jmp     short loc_180026791
0x1800267c6  lea     rcx, [rsp+270h+var_248]
0x1800267cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800267d0  movsxd  rcx, [rsp+270h+var_250]
0x1800267d5  movsxd  rax, [rsp+270h+var_24C]
0x1800267da  shl     rcx, 1Fh
0x1800267de  or      rcx, rax
0x1800267e1  mov     [rdi], rcx
0x1800267e4  xor     ebx, ebx
0x1800267e6  lea     rcx, [rsp+270h+var_240]
0x1800267eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800267f0  mov     eax, ebx
0x1800267f2  mov     rcx, [rbp+170h+var_20]
0x1800267f9  xor     rcx, rsp; StackCookie
0x1800267fc  call    __security_check_cookie
0x180026801  mov     rbx, [rsp+270h+arg_8]
0x180026809  add     rsp, 260h
0x180026810  pop     r14
0x180026812  pop     rdi
0x180026813  pop     rbp
0x180026814  retn
```

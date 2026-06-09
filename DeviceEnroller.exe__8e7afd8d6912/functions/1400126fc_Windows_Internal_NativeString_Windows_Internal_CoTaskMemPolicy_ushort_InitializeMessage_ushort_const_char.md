# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeMessage(ushort const *,char *)

- ea: `0x1400126fc`
- end: `0x1400127e9`
- name: `?InitializeMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGPEAD@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400127f0`

## callees

- `0x1400126fc`
- `0x14001ca80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001276e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001276e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140012764`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140012764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400127a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400127a8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
        __int64 a1,
        const void *a2,
        va_list a3)
{
  unsigned __int64 v6; // rcx
  unsigned __int64 *v7; // r14
  unsigned __int64 *v8; // rdi
  int v9; // ebx
  signed int LastError; // eax
  __int64 v11; // rax
  va_list Arguments; // [rsp+98h] [rbp+20h] BYREF

  v6 = 32;
  v7 = (unsigned __int64 *)(a1 + 16);
  v8 = (unsigned __int64 *)(a1 + 16);
  while ( 1 )
  {
    v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(a1, v6);
    if ( v9 < 0 )
      break;
    Arguments = a3;
    v8 = (unsigned __int64 *)(a1 + 16);
    if ( FormatMessageW(0x400u, a2, 0, 0, *(LPWSTR *)a1, *(_DWORD *)(a1 + 16), &Arguments) )
    {
      v9 = 0;
LABEL_14:
      if ( v9 >= 0 )
      {
        v11 = -1;
        goto LABEL_18;
      }
      break;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
    {
      v9 = -2147467259;
      goto LABEL_14;
    }
    if ( v9 != -2147024774 )
      goto LABEL_14;
    v6 = *v8 + 32;
    if ( v6 < *v8 )
    {
      v9 = -2147024362;
      break;
    }
  }
  if ( *(_QWORD *)a1 )
  {
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
  }
  else
  {
    v7 = v8;
  }
  *v7 = 0;
  v11 = 0;
LABEL_18:
  *(_QWORD *)(a1 + 8) = v11;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400126fc  push    rbx
0x1400126fe  push    rbp
0x1400126ff  push    rsi
0x140012700  push    rdi
0x140012701  push    r14
0x140012703  push    r15
0x140012705  sub     rsp, 48h
0x140012709  mov     rsi, rcx
0x14001270c  mov     rbp, r8
0x14001270f  mov     r15, rdx
0x140012712  mov     ecx, 20h ; ' '
0x140012717  lea     r14, [rsi+10h]
0x14001271b  mov     rdi, r14
0x14001271e  mov     rdx, rcx
0x140012721  mov     rcx, rsi
0x140012724  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x140012729  mov     ebx, eax
0x14001272b  test    eax, eax
0x14001272d  js      short loc_1400127A0
0x14001272f  lea     rcx, [rsp+78h+arg_18]
0x140012737  mov     [rsp+78h+arg_18], rbp
0x14001273f  mov     [rsp+78h+Arguments], rcx; Arguments
0x140012744  lea     rdi, [rsi+10h]
0x140012748  mov     eax, [rdi]
0x14001274a  xor     r9d, r9d; dwLanguageId
0x14001274d  mov     [rsp+78h+nSize], eax; nSize
0x140012751  xor     r8d, r8d; dwMessageId
0x140012754  mov     rax, [rsi]
0x140012757  mov     rdx, r15; lpSource
0x14001275a  mov     ecx, 400h; dwFlags
0x14001275f  mov     [rsp+78h+lpBuffer], rax; lpBuffer
0x140012764  call    cs:__imp_FormatMessageW
0x14001276a  test    eax, eax
0x14001276c  jnz     short loc_1400127BE
0x14001276e  call    cs:__imp_GetLastError
0x140012774  mov     ebx, eax
0x140012776  test    eax, eax
0x140012778  jle     short loc_140012783
0x14001277a  movzx   ebx, ax
0x14001277d  or      ebx, 80070000h
0x140012783  test    ebx, ebx
0x140012785  jns     short loc_1400127B7
0x140012787  cmp     ebx, 8007007Ah
0x14001278d  jnz     short loc_1400127C0
0x14001278f  mov     rax, [rdi]
0x140012792  lea     rcx, [rax+20h]
0x140012796  cmp     rcx, rax
0x140012799  jnb     short loc_14001271E
0x14001279b  mov     ebx, 80070216h
0x1400127a0  mov     rcx, [rsi]; pv
0x1400127a3  test    rcx, rcx
0x1400127a6  jz      short loc_1400127CA
0x1400127a8  call    cs:__imp_CoTaskMemFree
0x1400127ae  mov     qword ptr [rsi], 0
0x1400127b5  jmp     short loc_1400127CD
0x1400127b7  mov     ebx, 80004005h
0x1400127bc  jmp     short loc_1400127C0
0x1400127be  xor     ebx, ebx
0x1400127c0  test    ebx, ebx
0x1400127c2  js      short loc_1400127A0
0x1400127c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400127c8  jmp     short loc_1400127D6
0x1400127ca  mov     r14, rdi
0x1400127cd  mov     qword ptr [r14], 0
0x1400127d4  xor     eax, eax
0x1400127d6  mov     [rsi+8], rax
0x1400127da  mov     eax, ebx
0x1400127dc  add     rsp, 48h
0x1400127e0  pop     r15
0x1400127e2  pop     r14
0x1400127e4  pop     rdi
0x1400127e5  pop     rsi
0x1400127e6  pop     rbp
0x1400127e7  pop     rbx
0x1400127e8  retn
```

# _anonymous_namespace_::DecodeKey__TASK_STATISTICS_

- ea: `0x18001e2ec`
- end: `0x18001e486`
- name: `_anonymous_namespace_::DecodeKey__TASK_STATISTICS_`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18001e890`

## callees

- `0x180010208`
- `0x18001e2ec`
- `0x18001e8e8`

## import_xrefs

- `msvcrt!malloc` at `0x18001e3f9`
- `msvcrt!malloc` at `0x18001e3f9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e471`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e471`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001e3c8`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001e3c8`
- `RPCRT4!NdrMesTypeDecode3` at `0x18001e456`
- `RPCRT4!NdrMesTypeDecode3` at `0x18001e456`
- `RPCRT4!MesHandleFree` at `0x18001e3ec`
- `RPCRT4!MesHandleFree` at `0x18001e410`
- `RPCRT4!MesHandleFree` at `0x18001e466`
- `RPCRT4!MesHandleFree` at `0x18001e3ec`
- `RPCRT4!MesHandleFree` at `0x18001e410`
- `RPCRT4!MesHandleFree` at `0x18001e466`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e32e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e38e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e32e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e38e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall anonymous_namespace_::DecodeKey__TASK_STATISTICS_(HKEY *a1, __int64 a2, void **a3)
{
  LSTATUS result; // eax
  BYTE *lpData; // rbx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  void **v9; // rax
  RPC_STATUS v10; // eax
  _OWORD *v11; // rax
  handle_t Handle; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  int v14; // [rsp+5Ch] [rbp+2Ch]
  BYTE *v15; // [rsp+68h] [rbp+38h]

  v14 = HIDWORD(a2);
  cbData = 0;
  result = RegQueryValueExW(*a1, L"Statistics", 0, 0, 0, &cbData);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    lpData = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)&std::nothrow);
    v15 = lpData;
    if ( lpData )
    {
      v7 = RegQueryValueExW(*a1, L"Statistics", 0, 0, lpData, &cbData);
      v8 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          v8 = (unsigned __int16)v7 | 0x80070000;
      }
      else
      {
        Handle = 0;
        v9 = tlx::replace<void *,long (*)(void *),&long MesHandleFree(void *),0>(&Handle);
        v10 = MesDecodeBufferHandleCreate((char *)lpData, cbData, v9);
        v8 = v10;
        if ( v10 )
        {
          if ( v10 > 0 )
            v8 = (unsigned __int16)v10 | 0x80070000;
          if ( Handle )
            MesHandleFree(Handle);
        }
        else
        {
          v11 = malloc(0x28u);
          *a3 = v11;
          if ( v11 )
          {
            *v11 = 0;
            v11[1] = 0;
            *((_QWORD *)v11 + 4) = 0;
            NdrMesTypeDecode3(Handle, &stru_1800282E0, &pProxyInfo, (const unsigned int **)&off_180030000, 1u, *a3);
            if ( Handle )
              MesHandleFree(Handle);
            v8 = 0;
          }
          else
          {
            if ( Handle )
              MesHandleFree(Handle);
            v8 = -2147024882;
          }
        }
      }
      operator delete[](lpData);
      return v8;
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e2ec  mov     r11, rsp
0x18001e2ef  mov     [r11+18h], rbx
0x18001e2f3  mov     [r11+10h], rdx
0x18001e2f7  push    rbp
0x18001e2f8  push    rsi
0x18001e2f9  push    rdi
0x18001e2fa  mov     rbp, rsp
0x18001e2fd  sub     rsp, 30h
0x18001e301  mov     rsi, r8
0x18001e304  mov     rdi, rcx
0x18001e307  mov     [rbp+cbData], 0
0x18001e30e  lea     rax, [rbp+cbData]
0x18001e312  mov     [r11-20h], rax
0x18001e316  mov     qword ptr [r11-28h], 0
0x18001e31e  xor     r9d, r9d; lpType
0x18001e321  xor     r8d, r8d; lpReserved
0x18001e324  lea     rdx, aStatistics; "Statistics"
0x18001e32b  mov     rcx, [rcx]; hKey
0x18001e32e  call    cs:__imp_RegQueryValueExW
0x18001e334  test    eax, eax
0x18001e336  jz      short loc_18001E34B
0x18001e338  jle     loc_18001E479
0x18001e33e  movzx   eax, ax
0x18001e341  or      eax, 80070000h
0x18001e346  jmp     loc_18001E479
0x18001e34b  mov     ecx, [rbp+cbData]; unsigned __int64
0x18001e34e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e355  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001e35a  mov     rbx, rax
0x18001e35d  mov     [rbp+arg_18], rax
0x18001e361  test    rax, rax
0x18001e364  jnz     short loc_18001E370
0x18001e366  mov     eax, 8007000Eh
0x18001e36b  jmp     loc_18001E479
0x18001e370  lea     rax, [rbp+cbData]
0x18001e374  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001e379  mov     [rsp+30h+lpData], rbx; lpData
0x18001e37e  xor     r9d, r9d; lpType
0x18001e381  xor     r8d, r8d; lpReserved
0x18001e384  lea     rdx, aStatistics; "Statistics"
0x18001e38b  mov     rcx, [rdi]; hKey
0x18001e38e  call    cs:__imp_RegQueryValueExW
0x18001e394  mov     edi, eax
0x18001e396  test    eax, eax
0x18001e398  jz      short loc_18001E3AE
0x18001e39a  jle     loc_18001E46E
0x18001e3a0  movzx   edi, ax
0x18001e3a3  or      edi, 80070000h
0x18001e3a9  jmp     loc_18001E46E
0x18001e3ae  mov     [rbp+Handle], 0
0x18001e3b6  lea     rcx, [rbp+Handle]
0x18001e3ba  call    ??$replace@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@0@@Z; tlx::replace<void *,long (*)(void *),&MesHandleFree(void *),0>(tlx::auto_xxx<void *,long (*)(void *),&MesHandleFree(void *),0> &)
0x18001e3bf  mov     r8, rax; pHandle
0x18001e3c2  mov     edx, [rbp+cbData]; BufferSize
0x18001e3c5  mov     rcx, rbx; Buffer
0x18001e3c8  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001e3ce  mov     edi, eax
0x18001e3d0  test    eax, eax
0x18001e3d2  jz      short loc_18001E3F4
0x18001e3d4  jle     short loc_18001E3DF
0x18001e3d6  movzx   edi, ax
0x18001e3d9  or      edi, 80070000h
0x18001e3df  mov     rcx, [rbp+Handle]; Handle
0x18001e3e3  test    rcx, rcx
0x18001e3e6  jz      loc_18001E46E
0x18001e3ec  call    cs:__imp_MesHandleFree
0x18001e3f2  jmp     short loc_18001E46E
0x18001e3f4  mov     ecx, 28h ; '('; Size
0x18001e3f9  call    cs:__imp_malloc
0x18001e3ff  mov     [rsi], rax
0x18001e402  test    rax, rax
0x18001e405  jnz     short loc_18001E41D
0x18001e407  mov     rcx, [rbp+Handle]; Handle
0x18001e40b  test    rcx, rcx
0x18001e40e  jz      short loc_18001E416
0x18001e410  call    cs:__imp_MesHandleFree
0x18001e416  mov     edi, 8007000Eh
0x18001e41b  jmp     short loc_18001E46E
0x18001e41d  xorps   xmm0, xmm0
0x18001e420  xor     ecx, ecx
0x18001e422  movups  xmmword ptr [rax], xmm0
0x18001e425  movups  xmmword ptr [rax+10h], xmm0
0x18001e429  mov     [rax+20h], rcx
0x18001e42d  mov     rax, [rsi]
0x18001e430  mov     [rsp+30h+lpcbData], rax; pObject
0x18001e435  mov     dword ptr [rsp+30h+lpData], 1; nTypeIndex
0x18001e43d  lea     r9, off_180030000; ArrTypeOffset
0x18001e444  lea     r8, pProxyInfo; pProxyInfo
0x18001e44b  lea     rdx, stru_1800282E0; pPicklingInfo
0x18001e452  mov     rcx, [rbp+Handle]; Handle
0x18001e456  call    cs:__imp_NdrMesTypeDecode3
0x18001e45c  nop
0x18001e45d  mov     rcx, [rbp+Handle]; Handle
0x18001e461  test    rcx, rcx
0x18001e464  jz      short loc_18001E46C
0x18001e466  call    cs:__imp_MesHandleFree
0x18001e46c  xor     edi, edi
0x18001e46e  mov     rcx, rbx
0x18001e471  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e477  mov     eax, edi
0x18001e479  mov     rbx, [rsp+30h+arg_10]
0x18001e47e  add     rsp, 30h
0x18001e482  pop     rdi
0x18001e483  pop     rsi
0x18001e484  pop     rbp
0x18001e485  retn
```

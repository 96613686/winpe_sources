# _anonymous_namespace_::DecodeKey_Encoderv1::_TASK_SCHEDULE_

- ea: `0x18001e144`
- end: `0x18001e2e4`
- name: `_anonymous_namespace_::DecodeKey_Encoderv1::_TASK_SCHEDULE_`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18001e868`

## callees

- `0x180010208`
- `0x18001e144`
- `0x18001e8e8`
- `0x180020c02`

## import_xrefs

- `msvcrt!malloc` at `0x18001e255`
- `msvcrt!malloc` at `0x18001e255`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e2cc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e2cc`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001e221`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001e221`
- `RPCRT4!NdrMesTypeDecode3` at `0x18001e2b1`
- `RPCRT4!NdrMesTypeDecode3` at `0x18001e2b1`
- `RPCRT4!MesHandleFree` at `0x18001e246`
- `RPCRT4!MesHandleFree` at `0x18001e26d`
- `RPCRT4!MesHandleFree` at `0x18001e2c1`
- `RPCRT4!MesHandleFree` at `0x18001e246`
- `RPCRT4!MesHandleFree` at `0x18001e26d`
- `RPCRT4!MesHandleFree` at `0x18001e2c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e186`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e1e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e186`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e1e4`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::DecodeKey_Encoderv1::_TASK_SCHEDULE_(HKEY *a1, __int64 a2, void **a3)
{
  LSTATUS result; // eax
  BYTE *lpData; // rbx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  handle_t *v9; // rax
  RPC_STATUS v10; // eax
  void *v11; // rax
  handle_t Handle; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int v14; // [rsp+4Ch] [rbp+14h]

  v14 = HIDWORD(a2);
  cbData = 0;
  result = RegQueryValueExW(*a1, L"Schedule", 0, 0, 0, &cbData);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    lpData = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)&std::nothrow);
    if ( lpData )
    {
      v7 = RegQueryValueExW(*a1, L"Schedule", 0, 0, lpData, &cbData);
      v8 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          v8 = (unsigned __int16)v7 | 0x80070000;
      }
      else
      {
        Handle = 0;
        v9 = (handle_t *)tlx::replace<void *,long (*)(void *),&long MesHandleFree(void *),0>(&Handle);
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
          v11 = malloc(0x58u);
          *a3 = v11;
          if ( v11 )
          {
            memset_0(v11, 0, 0x58u);
            NdrMesTypeDecode3(
              Handle,
              &pPicklingInfo,
              &Encoderv1::TaskScheduler_ProxyInfo,
              (const unsigned int **)&ArrTypeOffset,
              0,
              *a3);
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
0x18001e144  mov     r11, rsp
0x18001e147  mov     [r11+18h], rbx
0x18001e14b  mov     [r11+20h], rsi
0x18001e14f  mov     [r11+10h], rdx
0x18001e153  push    rdi
0x18001e154  sub     rsp, 30h
0x18001e158  lea     rax, [r11+10h]
0x18001e15c  mov     [rsp+38h+cbData], 0
0x18001e164  mov     rsi, r8
0x18001e167  mov     [r11-10h], rax
0x18001e16b  mov     rdi, rcx
0x18001e16e  mov     qword ptr [r11-18h], 0
0x18001e176  mov     rcx, [rcx]; hKey
0x18001e179  lea     rdx, aSchedule; "Schedule"
0x18001e180  xor     r9d, r9d; lpType
0x18001e183  xor     r8d, r8d; lpReserved
0x18001e186  call    cs:__imp_RegQueryValueExW
0x18001e18c  test    eax, eax
0x18001e18e  jz      short loc_18001E1A3
0x18001e190  jle     loc_18001E2D4
0x18001e196  movzx   eax, ax
0x18001e199  or      eax, 80070000h
0x18001e19e  jmp     loc_18001E2D4
0x18001e1a3  mov     ecx, [rsp+38h+cbData]; unsigned __int64
0x18001e1a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e1ae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001e1b3  mov     rbx, rax
0x18001e1b6  test    rax, rax
0x18001e1b9  jnz     short loc_18001E1C5
0x18001e1bb  mov     eax, 8007000Eh
0x18001e1c0  jmp     loc_18001E2D4
0x18001e1c5  mov     rcx, [rdi]; hKey
0x18001e1c8  lea     rax, [rsp+38h+cbData]
0x18001e1cd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001e1d2  lea     rdx, aSchedule; "Schedule"
0x18001e1d9  xor     r9d, r9d; lpType
0x18001e1dc  mov     [rsp+38h+lpData], rbx; lpData
0x18001e1e1  xor     r8d, r8d; lpReserved
0x18001e1e4  call    cs:__imp_RegQueryValueExW
0x18001e1ea  mov     edi, eax
0x18001e1ec  test    eax, eax
0x18001e1ee  jz      short loc_18001E204
0x18001e1f0  jle     loc_18001E2C9
0x18001e1f6  movzx   edi, ax
0x18001e1f9  or      edi, 80070000h
0x18001e1ff  jmp     loc_18001E2C9
0x18001e204  lea     rcx, [rsp+38h+Handle]
0x18001e209  mov     [rsp+38h+Handle], 0
0x18001e212  call    ??$replace@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@0@@Z; tlx::replace<void *,long (*)(void *),&MesHandleFree(void *),0>(tlx::auto_xxx<void *,long (*)(void *),&MesHandleFree(void *),0> &)
0x18001e217  mov     edx, [rsp+38h+cbData]; BufferSize
0x18001e21b  mov     r8, rax; pHandle
0x18001e21e  mov     rcx, rbx; Buffer
0x18001e221  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001e227  mov     edi, eax
0x18001e229  test    eax, eax
0x18001e22b  jz      short loc_18001E24E
0x18001e22d  jle     short loc_18001E238
0x18001e22f  movzx   edi, ax
0x18001e232  or      edi, 80070000h
0x18001e238  mov     rcx, [rsp+38h+Handle]; Handle
0x18001e23d  test    rcx, rcx
0x18001e240  jz      loc_18001E2C9
0x18001e246  call    cs:__imp_MesHandleFree
0x18001e24c  jmp     short loc_18001E2C9
0x18001e24e  mov     edi, 58h ; 'X'
0x18001e253  mov     ecx, edi; Size
0x18001e255  call    cs:__imp_malloc
0x18001e25b  mov     [rsi], rax
0x18001e25e  test    rax, rax
0x18001e261  jnz     short loc_18001E27A
0x18001e263  mov     rcx, [rsp+38h+Handle]; Handle
0x18001e268  test    rcx, rcx
0x18001e26b  jz      short loc_18001E273
0x18001e26d  call    cs:__imp_MesHandleFree
0x18001e273  mov     edi, 8007000Eh
0x18001e278  jmp     short loc_18001E2C9
0x18001e27a  mov     r8, rdi; Size
0x18001e27d  xor     edx, edx; Val
0x18001e27f  mov     rcx, rax; void *
0x18001e282  call    memset_0
0x18001e287  mov     rax, [rsi]
0x18001e28a  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18001e291  mov     rcx, [rsp+38h+Handle]; Handle
0x18001e296  lea     r8, ?TaskScheduler_ProxyInfo@Encoderv1@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001e29d  mov     [rsp+38h+lpcbData], rax; pObject
0x18001e2a2  lea     rdx, pPicklingInfo; pPicklingInfo
0x18001e2a9  mov     dword ptr [rsp+38h+lpData], 0; nTypeIndex
0x18001e2b1  call    cs:__imp_NdrMesTypeDecode3
0x18001e2b7  mov     rcx, [rsp+38h+Handle]; Handle
0x18001e2bc  test    rcx, rcx
0x18001e2bf  jz      short loc_18001E2C7
0x18001e2c1  call    cs:__imp_MesHandleFree
0x18001e2c7  xor     edi, edi
0x18001e2c9  mov     rcx, rbx
0x18001e2cc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e2d2  mov     eax, edi
0x18001e2d4  mov     rbx, [rsp+38h+arg_10]
0x18001e2d9  mov     rsi, [rsp+38h+arg_18]
0x18001e2de  add     rsp, 30h
0x18001e2e2  pop     rdi
0x18001e2e3  retn
```

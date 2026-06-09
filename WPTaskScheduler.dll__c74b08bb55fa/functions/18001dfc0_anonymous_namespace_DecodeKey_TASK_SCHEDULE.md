# _anonymous_namespace_::DecodeKey__TASK_SCHEDULE_

- ea: `0x18001dfc0`
- end: `0x18001e13e`
- name: `_anonymous_namespace_::DecodeKey__TASK_SCHEDULE_`
- size: `382`
- prototype: `LSTATUS __fastcall(HKEY *, __int64, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18001e840`

## callees

- `0x180010208`
- `0x18001dfc0`
- `0x18001e8e8`
- `0x18001ed18`
- `0x180020c02`

## import_xrefs

- `msvcrt!malloc` at `0x18001e0cb`
- `msvcrt!malloc` at `0x18001e0cb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e129`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e129`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001e09c`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001e09c`
- `RPCRT4!MesHandleFree` at `0x18001e0bc`
- `RPCRT4!MesHandleFree` at `0x18001e0e2`
- `RPCRT4!MesHandleFree` at `0x18001e11e`
- `RPCRT4!MesHandleFree` at `0x18001e0bc`
- `RPCRT4!MesHandleFree` at `0x18001e0e2`
- `RPCRT4!MesHandleFree` at `0x18001e11e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e002`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e062`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e002`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e062`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::DecodeKey__TASK_SCHEDULE_(HKEY *a1, __int64 a2, void **a3)
{
  LSTATUS result; // eax
  BYTE *lpData; // rbx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  handle_t *v9; // rax
  RPC_STATUS v10; // eax
  void *v11; // rax
  handle_t Handle; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+6Ch] [rbp+2Ch]
  char *pBuffer; // [rsp+78h] [rbp+38h] BYREF

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
            pBuffer = (char *)lpData;
            anonymous_namespace_::Decode_0(Handle, &pBuffer, cbData, *a3);
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
0x18001dfc0  mov     r11, rsp
0x18001dfc3  mov     [r11+18h], rbx
0x18001dfc7  mov     [r11+10h], rdx
0x18001dfcb  push    rbp
0x18001dfcc  push    rsi
0x18001dfcd  push    rdi
0x18001dfce  mov     rbp, rsp
0x18001dfd1  sub     rsp, 40h
0x18001dfd5  mov     rsi, r8
0x18001dfd8  mov     rdi, rcx
0x18001dfdb  mov     [rbp+cbData], 0
0x18001dfe2  lea     rax, [rbp+cbData]
0x18001dfe6  mov     [r11-30h], rax
0x18001dfea  mov     qword ptr [r11-38h], 0
0x18001dff2  xor     r9d, r9d; lpType
0x18001dff5  xor     r8d, r8d; lpReserved
0x18001dff8  lea     rdx, aSchedule; "Schedule"
0x18001dfff  mov     rcx, [rcx]; hKey
0x18001e002  call    cs:__imp_RegQueryValueExW
0x18001e008  test    eax, eax
0x18001e00a  jz      short loc_18001E01F
0x18001e00c  jle     loc_18001E131
0x18001e012  movzx   eax, ax
0x18001e015  or      eax, 80070000h
0x18001e01a  jmp     loc_18001E131
0x18001e01f  mov     ecx, [rbp+cbData]; unsigned __int64
0x18001e022  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e029  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001e02e  mov     rbx, rax
0x18001e031  mov     [rbp+var_10], rax
0x18001e035  test    rax, rax
0x18001e038  jnz     short loc_18001E044
0x18001e03a  mov     eax, 8007000Eh
0x18001e03f  jmp     loc_18001E131
0x18001e044  lea     rax, [rbp+cbData]
0x18001e048  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001e04d  mov     [rsp+40h+lpData], rbx; lpData
0x18001e052  xor     r9d, r9d; lpType
0x18001e055  xor     r8d, r8d; lpReserved
0x18001e058  lea     rdx, aSchedule; "Schedule"
0x18001e05f  mov     rcx, [rdi]; hKey
0x18001e062  call    cs:__imp_RegQueryValueExW
0x18001e068  mov     edi, eax
0x18001e06a  test    eax, eax
0x18001e06c  jz      short loc_18001E082
0x18001e06e  jle     loc_18001E126
0x18001e074  movzx   edi, ax
0x18001e077  or      edi, 80070000h
0x18001e07d  jmp     loc_18001E126
0x18001e082  mov     [rbp+Handle], 0
0x18001e08a  lea     rcx, [rbp+Handle]
0x18001e08e  call    ??$replace@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@0@@Z; tlx::replace<void *,long (*)(void *),&MesHandleFree(void *),0>(tlx::auto_xxx<void *,long (*)(void *),&MesHandleFree(void *),0> &)
0x18001e093  mov     r8, rax; pHandle
0x18001e096  mov     edx, [rbp+cbData]; BufferSize
0x18001e099  mov     rcx, rbx; Buffer
0x18001e09c  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001e0a2  mov     edi, eax
0x18001e0a4  test    eax, eax
0x18001e0a6  jz      short loc_18001E0C4
0x18001e0a8  jle     short loc_18001E0B3
0x18001e0aa  movzx   edi, ax
0x18001e0ad  or      edi, 80070000h
0x18001e0b3  mov     rcx, [rbp+Handle]; Handle
0x18001e0b7  test    rcx, rcx
0x18001e0ba  jz      short loc_18001E126
0x18001e0bc  call    cs:__imp_MesHandleFree
0x18001e0c2  jmp     short loc_18001E126
0x18001e0c4  mov     edi, 58h ; 'X'
0x18001e0c9  mov     ecx, edi; Size
0x18001e0cb  call    cs:__imp_malloc
0x18001e0d1  mov     [rsi], rax
0x18001e0d4  test    rax, rax
0x18001e0d7  jnz     short loc_18001E0EF
0x18001e0d9  mov     rcx, [rbp+Handle]; Handle
0x18001e0dd  test    rcx, rcx
0x18001e0e0  jz      short loc_18001E0E8
0x18001e0e2  call    cs:__imp_MesHandleFree
0x18001e0e8  mov     edi, 8007000Eh
0x18001e0ed  jmp     short loc_18001E126
0x18001e0ef  mov     r8, rdi; Size
0x18001e0f2  xor     edx, edx; Val
0x18001e0f4  mov     rcx, rax; void *
0x18001e0f7  call    memset_0
0x18001e0fc  mov     [rbp+pBuffer], rbx
0x18001e100  mov     r9, [rsi]; pObject
0x18001e103  mov     r8d, [rbp+cbData]; BufferSize
0x18001e107  lea     rdx, [rbp+pBuffer]; pBuffer
0x18001e10b  mov     rcx, [rbp+Handle]; Handle
0x18001e10f  call    _anonymous_namespace___Decode_0
0x18001e114  nop
0x18001e115  mov     rcx, [rbp+Handle]; Handle
0x18001e119  test    rcx, rcx
0x18001e11c  jz      short loc_18001E124
0x18001e11e  call    cs:__imp_MesHandleFree
0x18001e124  xor     edi, edi
0x18001e126  mov     rcx, rbx
0x18001e129  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e12f  mov     eax, edi
0x18001e131  mov     rbx, [rsp+40h+arg_10]
0x18001e136  add     rsp, 40h
0x18001e13a  pop     rdi
0x18001e13b  pop     rsi
0x18001e13c  pop     rbp
0x18001e13d  retn
```

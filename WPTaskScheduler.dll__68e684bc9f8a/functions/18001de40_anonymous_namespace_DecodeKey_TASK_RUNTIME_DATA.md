# _anonymous_namespace_::DecodeKey__TASK_RUNTIME_DATA_

- ea: `0x18001de40`
- end: `0x18001dfb9`
- name: `_anonymous_namespace_::DecodeKey__TASK_RUNTIME_DATA_`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18001e818`

## callees

- `0x180010208`
- `0x18001de40`
- `0x18001e8e8`
- `0x18001ec18`

## import_xrefs

- `msvcrt!malloc` at `0x18001df49`
- `msvcrt!malloc` at `0x18001df49`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001dfa4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001dfa4`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001df1c`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001df1c`
- `RPCRT4!MesHandleFree` at `0x18001df3c`
- `RPCRT4!MesHandleFree` at `0x18001df60`
- `RPCRT4!MesHandleFree` at `0x18001df99`
- `RPCRT4!MesHandleFree` at `0x18001df3c`
- `RPCRT4!MesHandleFree` at `0x18001df60`
- `RPCRT4!MesHandleFree` at `0x18001df99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001de82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001dee2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001de82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001dee2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall anonymous_namespace_::DecodeKey__TASK_RUNTIME_DATA_(HKEY *a1, __int64 a2, _QWORD *a3)
{
  LSTATUS result; // eax
  BYTE *lpData; // rbx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  void **v9; // rax
  RPC_STATUS v10; // eax
  _OWORD *v11; // rax
  handle_t Handle; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+6Ch] [rbp+2Ch]
  char *pBuffer; // [rsp+78h] [rbp+38h] BYREF

  v14 = HIDWORD(a2);
  cbData = 0;
  result = RegQueryValueExW(*a1, L"RuntimeData", 0, 0, 0, &cbData);
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
      v7 = RegQueryValueExW(*a1, L"RuntimeData", 0, 0, lpData, &cbData);
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
          v11 = malloc(0x20u);
          *a3 = v11;
          if ( v11 )
          {
            *v11 = 0;
            v11[1] = 0;
            pBuffer = (char *)lpData;
            anonymous_namespace_::Decode(Handle, &pBuffer, cbData);
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
0x18001de40  mov     r11, rsp
0x18001de43  mov     [r11+18h], rbx
0x18001de47  mov     [r11+10h], rdx
0x18001de4b  push    rbp
0x18001de4c  push    rsi
0x18001de4d  push    rdi
0x18001de4e  mov     rbp, rsp
0x18001de51  sub     rsp, 40h
0x18001de55  mov     rsi, r8
0x18001de58  mov     rdi, rcx
0x18001de5b  mov     [rbp+cbData], 0
0x18001de62  lea     rax, [rbp+cbData]
0x18001de66  mov     [r11-30h], rax
0x18001de6a  mov     qword ptr [r11-38h], 0
0x18001de72  xor     r9d, r9d; lpType
0x18001de75  xor     r8d, r8d; lpReserved
0x18001de78  lea     rdx, aRuntimedata; "RuntimeData"
0x18001de7f  mov     rcx, [rcx]; hKey
0x18001de82  call    cs:__imp_RegQueryValueExW
0x18001de88  test    eax, eax
0x18001de8a  jz      short loc_18001DE9F
0x18001de8c  jle     loc_18001DFAC
0x18001de92  movzx   eax, ax
0x18001de95  or      eax, 80070000h
0x18001de9a  jmp     loc_18001DFAC
0x18001de9f  mov     ecx, [rbp+cbData]; unsigned __int64
0x18001dea2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dea9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001deae  mov     rbx, rax
0x18001deb1  mov     [rbp+var_10], rax
0x18001deb5  test    rax, rax
0x18001deb8  jnz     short loc_18001DEC4
0x18001deba  mov     eax, 8007000Eh
0x18001debf  jmp     loc_18001DFAC
0x18001dec4  lea     rax, [rbp+cbData]
0x18001dec8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001decd  mov     [rsp+40h+lpData], rbx; lpData
0x18001ded2  xor     r9d, r9d; lpType
0x18001ded5  xor     r8d, r8d; lpReserved
0x18001ded8  lea     rdx, aRuntimedata; "RuntimeData"
0x18001dedf  mov     rcx, [rdi]; hKey
0x18001dee2  call    cs:__imp_RegQueryValueExW
0x18001dee8  mov     edi, eax
0x18001deea  test    eax, eax
0x18001deec  jz      short loc_18001DF02
0x18001deee  jle     loc_18001DFA1
0x18001def4  movzx   edi, ax
0x18001def7  or      edi, 80070000h
0x18001defd  jmp     loc_18001DFA1
0x18001df02  mov     [rbp+Handle], 0
0x18001df0a  lea     rcx, [rbp+Handle]
0x18001df0e  call    ??$replace@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@0@@Z; tlx::replace<void *,long (*)(void *),&MesHandleFree(void *),0>(tlx::auto_xxx<void *,long (*)(void *),&MesHandleFree(void *),0> &)
0x18001df13  mov     r8, rax; pHandle
0x18001df16  mov     edx, [rbp+cbData]; BufferSize
0x18001df19  mov     rcx, rbx; Buffer
0x18001df1c  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001df22  mov     edi, eax
0x18001df24  test    eax, eax
0x18001df26  jz      short loc_18001DF44
0x18001df28  jle     short loc_18001DF33
0x18001df2a  movzx   edi, ax
0x18001df2d  or      edi, 80070000h
0x18001df33  mov     rcx, [rbp+Handle]; Handle
0x18001df37  test    rcx, rcx
0x18001df3a  jz      short loc_18001DFA1
0x18001df3c  call    cs:__imp_MesHandleFree
0x18001df42  jmp     short loc_18001DFA1
0x18001df44  mov     ecx, 20h ; ' '; Size
0x18001df49  call    cs:__imp_malloc
0x18001df4f  mov     [rsi], rax
0x18001df52  test    rax, rax
0x18001df55  jnz     short loc_18001DF6D
0x18001df57  mov     rcx, [rbp+Handle]; Handle
0x18001df5b  test    rcx, rcx
0x18001df5e  jz      short loc_18001DF66
0x18001df60  call    cs:__imp_MesHandleFree
0x18001df66  mov     edi, 8007000Eh
0x18001df6b  jmp     short loc_18001DFA1
0x18001df6d  xorps   xmm0, xmm0
0x18001df70  movups  xmmword ptr [rax], xmm0
0x18001df73  movups  xmmword ptr [rax+10h], xmm0
0x18001df77  mov     [rbp+pBuffer], rbx
0x18001df7b  mov     r9, [rsi]
0x18001df7e  mov     r8d, [rbp+cbData]; BufferSize
0x18001df82  lea     rdx, [rbp+pBuffer]; pBuffer
0x18001df86  mov     rcx, [rbp+Handle]; Handle
0x18001df8a  call    _anonymous_namespace___Decode
0x18001df8f  nop
0x18001df90  mov     rcx, [rbp+Handle]; Handle
0x18001df94  test    rcx, rcx
0x18001df97  jz      short loc_18001DF9F
0x18001df99  call    cs:__imp_MesHandleFree
0x18001df9f  xor     edi, edi
0x18001dfa1  mov     rcx, rbx
0x18001dfa4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001dfaa  mov     eax, edi
0x18001dfac  mov     rbx, [rsp+40h+arg_10]
0x18001dfb1  add     rsp, 40h
0x18001dfb5  pop     rdi
0x18001dfb6  pop     rsi
0x18001dfb7  pop     rbp
0x18001dfb8  retn
```

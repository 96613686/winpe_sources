# WsDeleteSymbolicLink

- ea: `0x180008c90`
- end: `0x180008de7`
- name: `WsDeleteSymbolicLink`
- size: `343`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180001710`
- `0x18002988c`
- `0x18002a54c`
- `0x18002a644`

## callees

- `0x180008484`
- `0x180008c90`
- `0x18002ecc0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008dc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008dc3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008ce7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008ce7`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180008cdb`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180008cdb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008cc6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008cc6`
- `RPCRT4!RpcImpersonateClient` at `0x180008d61`
- `RPCRT4!RpcImpersonateClient` at `0x180008d61`
- `RPCRT4!RpcRevertToSelf` at `0x180008d04`
- `RPCRT4!RpcRevertToSelf` at `0x180008d04`

## pseudocode

```c
void __fastcall WsDeleteSymbolicLink(__int64 a1, const WCHAR *a2, WCHAR *a3, void *a4)
{
  WCHAR *v5; // rbx
  char v7; // si
  RPC_STATUS v8; // eax
  int v9; // r8d
  RPC_STATUS v10; // eax
  int v11; // r8d

  v5 = a3;
  if ( !a1 && !a3 )
    return;
  v7 = 0;
  if ( !a3 )
  {
    v5 = (WCHAR *)WsReturnSessionPath();
    if ( !v5 )
      return;
    v7 = 1;
  }
  if ( a4 == (void *)-1LL )
  {
    v10 = RpcImpersonateClient(0);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v11, (unsigned int)"unknown", 0, v10);
      }
      goto LABEL_7;
    }
    goto LABEL_5;
  }
  if ( SetThreadToken(0, a4) )
  {
LABEL_5:
    DefineDosDeviceW(0xFu, v5, a2);
    if ( a4 == (void *)-1LL )
    {
      v8 = RpcRevertToSelf();
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v9, (unsigned int)"unknown", 0, v8);
        }
        __fastfail(7u);
      }
    }
    else
    {
      RevertToSelf();
    }
  }
LABEL_7:
  if ( v5 )
  {
    if ( v7 )
      LocalFree(v5);
  }
}

```

## disassembly

```asm
0x180008c90  push    rbx
0x180008c92  push    rbp
0x180008c93  push    rsi
0x180008c94  push    rdi
0x180008c95  sub     rsp, 38h
0x180008c99  mov     rdi, r9
0x180008c9c  mov     rbx, r8
0x180008c9f  mov     rbp, rdx
0x180008ca2  test    rcx, rcx
0x180008ca5  jz      loc_180008D57
0x180008cab  xor     sil, sil
0x180008cae  test    rbx, rbx
0x180008cb1  jz      loc_180008DCE
0x180008cb7  xor     ecx, ecx; BindingHandle
0x180008cb9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180008cbd  jz      loc_180008D61
0x180008cc3  mov     rdx, rdi; Token
0x180008cc6  call    cs:__imp_SetThreadToken
0x180008ccc  test    eax, eax
0x180008cce  jz      short loc_180008CED
0x180008cd0  mov     r8, rbp; lpTargetPath
0x180008cd3  mov     rdx, rbx; lpDeviceName
0x180008cd6  mov     ecx, 0Fh; dwFlags
0x180008cdb  call    cs:__imp_DefineDosDeviceW
0x180008ce1  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180008ce5  jz      short loc_180008D04
0x180008ce7  call    cs:__imp_RevertToSelf
0x180008ced  test    rbx, rbx
0x180008cf0  jz      short loc_180008CFB
0x180008cf2  test    sil, sil
0x180008cf5  jnz     loc_180008DC0
0x180008cfb  add     rsp, 38h
0x180008cff  pop     rdi
0x180008d00  pop     rsi
0x180008d01  pop     rbp
0x180008d02  pop     rbx
0x180008d03  retn
0x180008d04  call    cs:__imp_RpcRevertToSelf
0x180008d0a  test    eax, eax
0x180008d0c  jz      short loc_180008CED
0x180008d0e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180008d15  lea     rdx, WPP_GLOBAL_Control
0x180008d1c  cmp     rcx, rdx
0x180008d1f  jz      short loc_180008D4E
0x180008d21  test    byte ptr [rcx+1Ch], 4
0x180008d25  jz      short loc_180008D4E
0x180008d27  cmp     byte ptr [rcx+19h], 1
0x180008d2b  jb      short loc_180008D4E
0x180008d2d  mov     rcx, [rcx+10h]
0x180008d31  lea     r9, aUnknown; "unknown"
0x180008d38  mov     [rsp+58h+var_30], eax
0x180008d3c  mov     edx, 0Bh
0x180008d41  mov     [rsp+58h+var_38], 0
0x180008d49  call    WPP_SF_sdL
0x180008d4e  mov     ecx, 7
0x180008d53  int     29h; Win8: RtlFailFast(ecx)
0x180008d55  jmp     short loc_180008CED
0x180008d57  test    rbx, rbx
0x180008d5a  jz      short loc_180008CFB
0x180008d5c  jmp     loc_180008CAB
0x180008d61  call    cs:__imp_RpcImpersonateClient
0x180008d67  test    eax, eax
0x180008d69  jz      loc_180008CD0
0x180008d6f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180008d76  lea     rdx, WPP_GLOBAL_Control
0x180008d7d  cmp     rcx, rdx
0x180008d80  jz      loc_180008CED
0x180008d86  test    byte ptr [rcx+1Ch], 4
0x180008d8a  jz      loc_180008CED
0x180008d90  cmp     byte ptr [rcx+19h], 1
0x180008d94  jb      loc_180008CED
0x180008d9a  mov     rcx, [rcx+10h]
0x180008d9e  lea     r9, aUnknown; "unknown"
0x180008da5  mov     [rsp+58h+var_30], eax
0x180008da9  mov     edx, 0Ah
0x180008dae  mov     [rsp+58h+var_38], 0
0x180008db6  call    WPP_SF_sdL
0x180008dbb  jmp     loc_180008CED
0x180008dc0  mov     rcx, rbx; hMem
0x180008dc3  call    cs:__imp_LocalFree
0x180008dc9  jmp     loc_180008CFB
0x180008dce  call    WsReturnSessionPath
0x180008dd3  mov     rbx, rax
0x180008dd6  test    rax, rax
0x180008dd9  jz      loc_180008CFB
0x180008ddf  mov     sil, 1
0x180008de2  jmp     loc_180008CB7
```

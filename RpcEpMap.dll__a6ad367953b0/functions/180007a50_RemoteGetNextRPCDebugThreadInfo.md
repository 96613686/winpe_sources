# RemoteGetNextRPCDebugThreadInfo

- ea: `0x180007a50`
- end: `0x180007b20`
- name: `RemoteGetNextRPCDebugThreadInfo`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004dc0`
- `0x180007a50`
- `0x180009bf8`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180007a8f`
- `RPCRT4!RpcRaiseException` at `0x180007b19`
- `RPCRT4!RpcRaiseException` at `0x180007a8f`
- `RPCRT4!RpcRaiseException` at `0x180007b19`

## pseudocode

```c
__int64 __fastcall RemoteGetNextRPCDebugThreadInfo(__int64 a1, _QWORD *a2, struct tagDebugCellID *a3, _DWORD *a4)
{
  unsigned int v7; // edi
  __int64 v8; // r15
  struct tagDebugCellUnion *NextDebugCellInfo; // rax
  struct tagDebugCellUnion *v10; // rbx
  char *v11; // rax

  if ( !a2 || *a2 )
    RpcRaiseException(87);
  *a2 = 0;
  *(_DWORD *)a3 = 0;
  v7 = 2;
  if ( *(_DWORD *)a1 != 2 )
    RpcRaiseException(6);
  v8 = *(_QWORD *)(a1 + 8);
  while ( 1 )
  {
    *a4 = *(_DWORD *)v8;
    NextDebugCellInfo = GetNextDebugCellInfo(*(void **)(v8 + 8), a3);
    v10 = NextDebugCellInfo;
    if ( !NextDebugCellInfo )
      break;
    if ( *(_BYTE *)NextDebugCellInfo == 3
      && (!*(_DWORD *)(v8 + 4) || *((unsigned __int16 *)NextDebugCellInfo + 6) == *(_DWORD *)(v8 + 4)) )
    {
      v11 = (char *)MIDL_user_allocate(0x10u);
      *a2 = v11;
      if ( v11 )
      {
        v7 = 0;
        *v11 = *(_BYTE *)v10;
        *((_WORD *)v11 + 1) = *((_WORD *)v10 + 1);
        *((_DWORD *)v11 + 1) = *((_DWORD *)v10 + 1);
        *((_WORD *)v11 + 4) = *((_WORD *)v10 + 6);
        *(_DWORD *)(v11 + 10) = *((_DWORD *)v10 + 2);
      }
      else
      {
        return 14;
      }
      return v7;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180007a50  push    rbx
0x180007a52  push    rbp
0x180007a53  push    rsi
0x180007a54  push    rdi
0x180007a55  push    r14
0x180007a57  push    r15
0x180007a59  sub     rsp, 28h
0x180007a5d  mov     rbp, r9
0x180007a60  mov     r14, r8
0x180007a63  mov     rsi, rdx
0x180007a66  test    rdx, rdx
0x180007a69  jz      loc_180007B14
0x180007a6f  cmp     qword ptr [rdx], 0
0x180007a73  jnz     loc_180007B14
0x180007a79  xor     eax, eax
0x180007a7b  mov     qword ptr [rdx], 0
0x180007a82  mov     [r8], eax
0x180007a85  lea     edi, [rax+2]
0x180007a88  cmp     [rcx], edi
0x180007a8a  jz      short loc_180007A96
0x180007a8c  lea     ecx, [rax+6]; exception
0x180007a8f  call    cs:__imp_RpcRaiseException
0x180007a95  int     3; Trap to Debugger
0x180007a96  mov     r15, [rcx+8]
0x180007a9a  mov     eax, [r15]
0x180007a9d  mov     rdx, r14; struct tagDebugCellID *
0x180007aa0  mov     [rbp+0], eax
0x180007aa3  mov     rcx, [r15+8]; void *
0x180007aa7  call    ?GetNextDebugCellInfo@@YAPEAUtagDebugCellUnion@@PEAXPEAUtagDebugCellID@@@Z; GetNextDebugCellInfo(void *,tagDebugCellID *)
0x180007aac  mov     rbx, rax
0x180007aaf  test    rax, rax
0x180007ab2  jz      short loc_180007B05
0x180007ab4  cmp     byte ptr [rax], 3
0x180007ab7  jnz     short loc_180007A9A
0x180007ab9  cmp     dword ptr [r15+4], 0
0x180007abe  jz      short loc_180007ACA
0x180007ac0  movzx   ecx, word ptr [rax+0Ch]
0x180007ac4  cmp     ecx, [r15+4]
0x180007ac8  jnz     short loc_180007A9A
0x180007aca  mov     ecx, 10h; size
0x180007acf  call    MIDL_user_allocate
0x180007ad4  mov     [rsi], rax
0x180007ad7  test    rax, rax
0x180007ada  jz      short loc_180007B00
0x180007adc  mov     cl, [rbx]
0x180007ade  xor     edi, edi
0x180007ae0  mov     [rax], cl
0x180007ae2  movzx   ecx, word ptr [rbx+2]
0x180007ae6  mov     [rax+2], cx
0x180007aea  mov     ecx, [rbx+4]
0x180007aed  mov     [rax+4], ecx
0x180007af0  movzx   ecx, word ptr [rbx+0Ch]
0x180007af4  mov     [rax+8], cx
0x180007af8  mov     ecx, [rbx+8]
0x180007afb  mov     [rax+0Ah], ecx
0x180007afe  jmp     short loc_180007B05
0x180007b00  mov     edi, 0Eh
0x180007b05  mov     eax, edi
0x180007b07  add     rsp, 28h
0x180007b0b  pop     r15
0x180007b0d  pop     r14
0x180007b0f  pop     rdi
0x180007b10  pop     rsi
0x180007b11  pop     rbp
0x180007b12  pop     rbx
0x180007b13  retn
0x180007b14  mov     ecx, 57h ; 'W'; exception
0x180007b19  call    cs:__imp_RpcRaiseException
```

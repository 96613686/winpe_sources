# WinHttpTransport::ReadResponseData(ulong)

- ea: `0x180053e60`
- end: `0x180053f80`
- name: `?ReadResponseData@WinHttpTransport@@AEAAJK@Z`
- size: `288`
- prototype: `int(WinHttpTransport *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180053750`

## callees

- `0x180007d4c`
- `0x1800256d0`
- `0x1800530c0`
- `0x180053e60`
- `0x180071e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f31`
- `WINHTTP!WinHttpReadData` at `0x180053f24`
- `WINHTTP!WinHttpReadData` at `0x180053f24`

## pseudocode

```c
__int64 __fastcall WinHttpTransport::ReadResponseData(WinHttpTransport *this, unsigned int a2)
{
  unsigned __int64 v3; // r15
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 *v6; // rcx
  _QWORD *v7; // rsi
  DWORD *v8; // r14
  void *v9; // rdi
  signed int LastError; // eax
  int v12; // [rsp+30h] [rbp-58h]

  v3 = a2;
  if ( !*((_QWORD *)this + 4) )
  {
    v4 = -2147187583;
    v12 = 518;
LABEL_3:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v4, "winhttptransport.cpp", v12, "HRESULT", &base);
    return v4;
  }
  v5 = ATL::CAtlList<WinHttpTransport::SecureBufferChunk,ATL::CElementTraits<WinHttpTransport::SecureBufferChunk>>::NewNode(
         (char *)this + 64,
         *((_QWORD *)this + 9));
  v6 = (__int64 *)*((_QWORD *)this + 9);
  if ( v6 )
    *v6 = v5;
  else
    *((_QWORD *)this + 8) = v5;
  *((_QWORD *)this + 9) = v5;
  if ( !v5 )
    return 0;
  v7 = (_QWORD *)(v5 + 16);
  v8 = (DWORD *)(v5 + 40);
  *(_DWORD *)(v5 + 40) = v3;
  v9 = PluginLocalAlloc(v3);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(v7);
  *v7 = v9;
  v7[1] = v3;
  if ( WinHttpReadData(*((HINTERNET *)this + 4), v9, v3, v8) )
    return 0;
  *v8 = 0;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    v12 = 531;
    goto LABEL_3;
  }
  return v4;
}

```

## disassembly

```asm
0x180053e60  push    rbx
0x180053e62  push    rbp
0x180053e63  push    rsi
0x180053e64  push    rdi
0x180053e65  push    r14
0x180053e67  push    r15
0x180053e69  sub     rsp, 58h
0x180053e6d  cmp     qword ptr [rcx+20h], 0
0x180053e72  mov     rbp, rcx
0x180053e75  mov     r15d, edx
0x180053e78  jnz     short loc_180053ECA
0x180053e7a  lea     rax, base
0x180053e81  mov     ebx, 80048481h
0x180053e86  mov     [rsp+88h+var_48], rax
0x180053e8b  lea     rax, aHresult; "HRESULT"
0x180053e92  mov     [rsp+88h+var_50], rax
0x180053e97  mov     [rsp+88h+var_58], 206h
0x180053e9f  lea     rax, aOnecoreuapDsEx_38+21h; "winhttptransport.cpp"
0x180053ea6  mov     ecx, 2
0x180053eab  mov     [rsp+88h+var_60], rax
0x180053eb0  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180053eb7  mov     r9d, ecx
0x180053eba  mov     [rsp+88h+var_68], ebx
0x180053ebe  xor     edx, edx
0x180053ec0  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180053ec5  jmp     loc_180053F71
0x180053eca  mov     rdx, [rcx+48h]
0x180053ece  add     rcx, 40h ; '@'
0x180053ed2  call    ?NewNode@?$CAtlList@USecureBufferChunk@WinHttpTransport@@V?$CElementTraits@USecureBufferChunk@WinHttpTransport@@@ATL@@@ATL@@AEAAPEAVCNode@12@PEAV312@0@Z; ATL::CAtlList<WinHttpTransport::SecureBufferChunk,ATL::CElementTraits<WinHttpTransport::SecureBufferChunk>>::NewNode(ATL::CAtlList<WinHttpTransport::SecureBufferChunk,ATL::CElementTraits<WinHttpTransport::SecureBufferChunk>>::CNode *,ATL::CAtlList<WinHttpTransport::SecureBufferChunk,ATL::CElementTraits<WinHttpTransport::SecureBufferChunk>>::CNode *)
0x180053ed7  mov     rcx, [rbp+48h]
0x180053edb  test    rcx, rcx
0x180053ede  jz      short loc_180053EE5
0x180053ee0  mov     [rcx], rax
0x180053ee3  jmp     short loc_180053EE9
0x180053ee5  mov     [rbp+40h], rax
0x180053ee9  mov     [rbp+48h], rax
0x180053eed  test    rax, rax
0x180053ef0  jz      short loc_180053F6F
0x180053ef2  lea     rsi, [rax+10h]
0x180053ef6  mov     rcx, r15; unsigned __int64
0x180053ef9  lea     r14, [rsi+18h]
0x180053efd  mov     [r14], r15d
0x180053f00  call    ?PluginLocalAlloc@@YAPEAX_K@Z; PluginLocalAlloc(unsigned __int64)
0x180053f05  mov     rcx, rsi
0x180053f08  mov     rdi, rax
0x180053f0b  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180053f10  mov     [rsi], rdi
0x180053f13  mov     r9, r14; lpdwNumberOfBytesRead
0x180053f16  mov     [rsi+8], r15
0x180053f1a  mov     r8d, r15d; dwNumberOfBytesToRead
0x180053f1d  mov     rcx, [rbp+20h]; hRequest
0x180053f21  mov     rdx, rdi; lpBuffer
0x180053f24  call    cs:__imp_WinHttpReadData
0x180053f2a  test    eax, eax
0x180053f2c  jnz     short loc_180053F6F
0x180053f2e  mov     [r14], eax
0x180053f31  call    cs:__imp_GetLastError
0x180053f37  mov     ebx, eax
0x180053f39  test    eax, eax
0x180053f3b  jle     short loc_180053F46
0x180053f3d  movzx   ebx, ax
0x180053f40  or      ebx, 80070000h
0x180053f46  test    ebx, ebx
0x180053f48  jns     short loc_180053F71
0x180053f4a  lea     rax, base
0x180053f51  mov     [rsp+88h+var_48], rax
0x180053f56  lea     rax, aHresult; "HRESULT"
0x180053f5d  mov     [rsp+88h+var_50], rax
0x180053f62  mov     [rsp+88h+var_58], 213h
0x180053f6a  jmp     loc_180053E9F
0x180053f6f  xor     ebx, ebx
0x180053f71  mov     eax, ebx
0x180053f73  add     rsp, 58h
0x180053f77  pop     r15
0x180053f79  pop     r14
0x180053f7b  pop     rdi
0x180053f7c  pop     rsi
0x180053f7d  pop     rbp
0x180053f7e  pop     rbx
0x180053f7f  retn
```

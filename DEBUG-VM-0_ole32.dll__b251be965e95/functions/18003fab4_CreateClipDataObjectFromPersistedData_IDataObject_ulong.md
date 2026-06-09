# CreateClipDataObjectFromPersistedData(IDataObject * *,ulong *)

- ea: `0x18003fab4`
- end: `0x18003fbb5`
- name: `?CreateClipDataObjectFromPersistedData@@YAJPEAPEAUIDataObject@@PEAK@Z`
- size: `257`
- prototype: `HRESULT __fastcall(IDataObject **ppDataObj, unsigned int *pdwClipSequenceNumber)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b3a0`

## callees

- `0x18000d38c`
- `0x18000ebc8`
- `0x1800185ec`
- `0x18002c4e4`
- `0x18003fab4`
- `0x1800405d4`
- `0x18008dc90`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18003fb00`
- `KERNELBASE!Sleep` at `0x18003fb00`
- `USER32!GetClipboardData` at `0x18003fb3f`
- `USER32!GetClipboardData` at `0x18003fb3f`
- `USER32!GetClipboardSequenceNumber` at `0x18003fac4`
- `USER32!GetClipboardSequenceNumber` at `0x18003fac4`
- `USER32!OpenClipboard` at `0x18003faf4`
- `USER32!OpenClipboard` at `0x18003fb09`
- `USER32!OpenClipboard` at `0x18003faf4`
- `USER32!OpenClipboard` at `0x18003fb09`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18003fb1f`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18003fb1f`

## string_xrefs

- `0x18003fb69`: `com\ole32\ole232\clipbrd\clipapi.cpp`

## pseudocode

```c
__int64 __fastcall CreateClipDataObjectFromPersistedData(IDataObject **ppDataObj, unsigned int *pdwClipSequenceNumber)
{
  DWORD ClipboardSequenceNumber; // eax
  HWND PrivateClipboardWindow; // rax
  HWND v6; // rbx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  unsigned int v9; // edx
  HANDLE ClipboardData; // rax
  void *v11; // rbx
  HRESULT v12; // r9d
  int PersistedDataObjectFromHGlobal; // eax
  void *retaddr; // [rsp+28h] [rbp+0h]
  OleClipboardLock clipLock; // [rsp+30h] [rbp+8h] BYREF

  ClipboardSequenceNumber = GetClipboardSequenceNumber();
  clipLock.m_locked = 0;
  *pdwClipSequenceNumber = ClipboardSequenceNumber;
  *ppDataObj = 0;
  PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
  v6 = PrivateClipboardWindow;
  if ( !PrivateClipboardWindow )
  {
    v7 = -2147467259;
LABEL_6:
    v9 = 3146;
LABEL_11:
    v12 = v7;
    goto LABEL_12;
  }
  if ( !OpenClipboard(PrivateClipboardWindow) )
  {
    Sleep(0);
    if ( !OpenClipboard(v6) )
    {
      v7 = -2147221040;
      goto LABEL_6;
    }
  }
  if ( (unsigned int)EdpGetIsManaged(v8) )
    EdpInlSetCurrentThreadPolicyEvaluation(1);
  clipLock.m_locked = 1;
  ClipboardData = GetClipboardData(g_cfMoreOlePrivateData);
  v11 = UtDupGlobal(ClipboardData, 0);
  if ( !v11 )
  {
    v7 = -2147024882;
    v9 = 3153;
    goto LABEL_11;
  }
  OleClipboardLock::Release(&clipLock);
  PersistedDataObjectFromHGlobal = LoadPersistedDataObjectFromHGlobal(v11, ppDataObj);
  v7 = PersistedDataObjectFromHGlobal;
  if ( PersistedDataObjectFromHGlobal >= 0 )
  {
    v7 = 0;
    goto LABEL_16;
  }
  v12 = PersistedDataObjectFromHGlobal;
  v9 = 3159;
LABEL_12:
  wil::details::in1diag3::Return_Hr(retaddr, v9, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", v12);
LABEL_16:
  OleClipboardLock::Release(&clipLock);
  return v7;
}

```

## disassembly

```asm
0x18003fab4  mov     [rsp+arg_8], rbx
0x18003fab9  push    rdi
0x18003faba  sub     rsp, 20h
0x18003fabe  mov     rbx, pdwClipSequenceNumber
0x18003fac1  mov     rdi, ppDataObj
0x18003fac4  call    cs:__imp_GetClipboardSequenceNumber
0x18003faca  mov     ecx, 1; fFlags
0x18003facf  mov     [rsp+28h+clipLock.m_locked], 0
0x18003fad4  mov     [rbx], eax
0x18003fad6  mov     qword ptr [rdi], 0
0x18003fadd  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18003fae2  mov     rbx, rax
0x18003fae5  test    rax, rax
0x18003fae8  jnz     short loc_18003FAF1
0x18003faea  mov     ebx, 80004005h
0x18003faef  jmp     short loc_18003FB18
0x18003faf1  mov     ppDataObj, rbx; hWndNewOwner
0x18003faf4  call    cs:__imp_OpenClipboard
0x18003fafa  test    eax, eax
0x18003fafc  jnz     short loc_18003FB1F
0x18003fafe  xor     ecx, ecx; dwMilliseconds
0x18003fb00  call    cs:__imp_Sleep
0x18003fb06  mov     ppDataObj, rbx; hWndNewOwner
0x18003fb09  call    cs:__imp_OpenClipboard
0x18003fb0f  test    eax, eax
0x18003fb11  jnz     short loc_18003FB1F
0x18003fb13  mov     ebx, 800401D0h
0x18003fb18  mov     edx, 0C4Ah
0x18003fb1d  jmp     short loc_18003FB61
0x18003fb1f  call    cs:__imp_EdpGetIsManaged
0x18003fb25  test    eax, eax
0x18003fb27  jz      short loc_18003FB33
0x18003fb29  mov     ecx, 1; EvaluationDisabled
0x18003fb2e  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18003fb33  movzx   ecx, cs:?g_cfMoreOlePrivateData@@3GA; uFormat
0x18003fb3a  mov     [rsp+28h+clipLock.m_locked], 1
0x18003fb3f  call    cs:__imp_GetClipboardData
0x18003fb45  mov     ppDataObj, rax; hsrc
0x18003fb48  xor     edx, edx; uiFlags
0x18003fb4a  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x18003fb4f  mov     rbx, rax
0x18003fb52  test    rax, rax
0x18003fb55  jnz     short loc_18003FB77
0x18003fb57  mov     ebx, 8007000Eh
0x18003fb5c  mov     edx, 0C51h; lineNumber
0x18003fb61  mov     r9d, ebx; hr
0x18003fb64  mov     ppDataObj, [rsp+28h]; callerReturnAddress
0x18003fb69  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18003fb70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fb75  jmp     short loc_18003FB9E
0x18003fb77  lea     ppDataObj, [rsp+28h+clipLock]; this
0x18003fb7c  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18003fb81  mov     pdwClipSequenceNumber, rdi; ppDataObj
0x18003fb84  mov     ppDataObj, rbx; hMorePrivateData
0x18003fb87  call    ?LoadPersistedDataObjectFromHGlobal@@YAJPEAXPEAPEAUIDataObject@@@Z; LoadPersistedDataObjectFromHGlobal(void *,IDataObject * *)
0x18003fb8c  mov     ebx, eax
0x18003fb8e  test    eax, eax
0x18003fb90  jns     short loc_18003FB9C
0x18003fb92  mov     r9d, eax
0x18003fb95  mov     edx, 0C57h
0x18003fb9a  jmp     short loc_18003FB64
0x18003fb9c  xor     ebx, ebx
0x18003fb9e  lea     ppDataObj, [rsp+28h+clipLock]; this
0x18003fba3  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18003fba8  mov     eax, ebx
0x18003fbaa  mov     rbx, [rsp+28h+arg_8]
0x18003fbaf  add     rsp, 20h
0x18003fbb3  pop     rdi
0x18003fbb4  retn
```

# CreateWrapperClipDataObjectFromFormatsArray(IDataObject * *,bool,ulong *)

- ea: `0x18000cf5c`
- end: `0x18000d11b`
- name: `?CreateWrapperClipDataObjectFromFormatsArray@@YAJPEAPEAUIDataObject@@_NPEAK@Z`
- size: `447`
- prototype: `HRESULT __fastcall(IDataObject **ppDataObj, bool isBrokeredCall, unsigned int *pdwClipSequenceNumber)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b3a0`
- `0x180010950`

## callees

- `0x18000b2d4`
- `0x18000cf5c`
- `0x18000d124`
- `0x18000d38c`
- `0x18000ebc8`
- `0x18002dd04`
- `0x180033a80`
- `0x1800405d4`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18000d0b7`
- `KERNELBASE!Sleep` at `0x18000d0b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d110`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d110`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d048`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0d5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000d06f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000d06f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000cff9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000cff9`
- `USER32!IsClipboardFormatAvailable` at `0x18000cfcf`
- `USER32!IsClipboardFormatAvailable` at `0x18000cfcf`
- `USER32!GetClipboardData` at `0x18000cfe4`
- `USER32!GetClipboardData` at `0x18000cfe4`
- `USER32!GetClipboardSequenceNumber` at `0x18000cf76`
- `USER32!GetClipboardSequenceNumber` at `0x18000cf76`
- `USER32!OpenClipboard` at `0x18000cfa5`
- `USER32!OpenClipboard` at `0x18000d0c0`
- `USER32!OpenClipboard` at `0x18000cfa5`
- `USER32!OpenClipboard` at `0x18000d0c0`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000cfb3`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000cfb3`

## pseudocode

```c
__int64 __fastcall CreateWrapperClipDataObjectFromFormatsArray(
        IDataObject **ppDataObj,
        CreateClipDataObjectOptions isBrokeredCall,
        unsigned int *pdwClipSequenceNumber)
{
  DWORD ClipboardSequenceNumber; // eax
  HWND PrivateClipboardWindow; // rax
  HWND v8; // rbx
  __int64 v9; // rcx
  FORMATETCDATAARRAY *v10; // rdi
  HANDLE ClipboardData; // rax
  void *v12; // rbp
  FORMATETCDATAARRAY *v13; // rax
  FORMATETCDATAARRAY *v14; // rsi
  FORMATETCDATAARRAY *v15; // rax
  signed int v16; // ebx
  signed int LastError; // eax
  OleClipboardLock clipLock; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 stSize; // [rsp+60h] [rbp+18h] BYREF

  ClipboardSequenceNumber = GetClipboardSequenceNumber();
  clipLock.m_locked = 0;
  *pdwClipSequenceNumber = ClipboardSequenceNumber;
  *ppDataObj = 0;
  PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
  v8 = PrivateClipboardWindow;
  if ( !PrivateClipboardWindow )
  {
    v16 = -2147467259;
    goto LABEL_17;
  }
  if ( !OpenClipboard(PrivateClipboardWindow) )
  {
    Sleep(0);
    if ( !OpenClipboard(v8) )
    {
      v16 = -2147221040;
      goto LABEL_17;
    }
  }
  if ( (unsigned int)EdpGetIsManaged(v9) )
    EdpInlSetCurrentThreadPolicyEvaluation(1);
  clipLock.m_locked = 1;
  v10 = 0;
  if ( !IsClipboardFormatAvailable(g_cfOlePrivateData) )
    goto LABEL_16;
  ClipboardData = GetClipboardData(g_cfOlePrivateData);
  v12 = ClipboardData;
  if ( !ClipboardData )
    goto LABEL_16;
  v13 = (FORMATETCDATAARRAY *)GlobalLock(ClipboardData);
  v14 = v13;
  if ( v13 )
  {
    if ( !v13->_dwSig && v13->_dwSize )
    {
      stSize = 0;
      if ( GetCopiedFormatEtcDataArraySize(v13, &stSize) >= 0
        && stSize < GetSafeAllocSize()
        && (v15 = (FORMATETCDATAARRAY *)HeapAlloc(g_hHeap, 0, stSize), (v10 = v15) != 0) )
      {
        v16 = 0;
        CopyFormatEtcDataArray(v15, v14, stSize, 1);
      }
      else
      {
        v16 = -2147024882;
      }
      GlobalUnlock(v12);
      goto LABEL_15;
    }
LABEL_16:
    v16 = CClipDataObject::Create(v10, isBrokeredCall, ppDataObj);
    if ( v16 >= 0 )
      goto LABEL_17;
    goto LABEL_24;
  }
  LastError = GetLastError();
  v16 = LastError;
  if ( LastError > 0 )
    v16 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
  if ( v16 >= 0 )
    goto LABEL_16;
LABEL_24:
  if ( v10 )
    HeapFree(g_hHeap, 0, v10);
LABEL_17:
  OleClipboardLock::Release(&clipLock);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000cf5c  mov     [rsp+arg_8], rbx
0x18000cf61  push    rbp
0x18000cf62  push    rsi
0x18000cf63  push    rdi
0x18000cf64  push    r12
0x18000cf66  push    r15
0x18000cf68  sub     rsp, 20h
0x18000cf6c  mov     rbx, pdwClipSequenceNumber
0x18000cf6f  movzx   r12d, isBrokeredCall
0x18000cf73  mov     r15, ppDataObj
0x18000cf76  call    cs:__imp_GetClipboardSequenceNumber
0x18000cf7c  mov     edi, 1
0x18000cf81  mov     [rsp+48h+clipLock.m_locked], 0
0x18000cf86  mov     [rbx], eax
0x18000cf88  mov     ecx, edi; fFlags
0x18000cf8a  mov     qword ptr [r15], 0
0x18000cf91  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18000cf96  mov     rbx, rax
0x18000cf99  test    rax, rax
0x18000cf9c  jz      loc_18000D0EC
0x18000cfa2  mov     ppDataObj, rax; hWndNewOwner
0x18000cfa5  call    cs:__imp_OpenClipboard
0x18000cfab  test    eax, eax
0x18000cfad  jz      loc_18000D0B5
0x18000cfb3  call    cs:__imp_EdpGetIsManaged
0x18000cfb9  test    eax, eax
0x18000cfbb  jnz     loc_18000D0F3
0x18000cfc1  movzx   ecx, cs:?g_cfOlePrivateData@@3GA; format
0x18000cfc8  mov     [rsp+48h+clipLock.m_locked], dil
0x18000cfcd  xor     edi, edi
0x18000cfcf  call    cs:__imp_IsClipboardFormatAvailable
0x18000cfd5  test    eax, eax
0x18000cfd7  jz      loc_18000D07D
0x18000cfdd  movzx   ecx, cs:?g_cfOlePrivateData@@3GA; uFormat
0x18000cfe4  call    cs:__imp_GetClipboardData
0x18000cfea  mov     rbp, rax
0x18000cfed  test    rax, rax
0x18000cff0  jz      loc_18000D07D
0x18000cff6  mov     ppDataObj, rax; hMem
0x18000cff9  call    cs:__imp_GlobalLock
0x18000cfff  mov     rsi, rax
0x18000d002  test    rax, rax
0x18000d005  jz      loc_18000D0D5
0x18000d00b  cmp     [rax], edi
0x18000d00d  jnz     short loc_18000D07D
0x18000d00f  cmp     [rax+4], edi
0x18000d012  jbe     short loc_18000D07D
0x18000d014  lea     rdx, [rsp+48h+stSize]; pstSize
0x18000d019  mov     [rsp+48h+stSize], rdi
0x18000d01e  mov     ppDataObj, rax; pClipFormatEtcDataArray
0x18000d021  call    ?GetCopiedFormatEtcDataArraySize@@YAJPEAUFORMATETCDATAARRAY@@PEA_K@Z; GetCopiedFormatEtcDataArraySize(FORMATETCDATAARRAY *,unsigned __int64 *)
0x18000d026  test    eax, eax
0x18000d028  js      loc_18000D0AE
0x18000d02e  call    GetSafeAllocSize
0x18000d033  cmp     [rsp+48h+stSize], rax
0x18000d038  jnb     short loc_18000D0AE
0x18000d03a  mov     pdwClipSequenceNumber, [rsp+48h+stSize]; dwBytes
0x18000d03f  xor     edx, edx; dwFlags
0x18000d041  mov     ppDataObj, cs:?g_hHeap@@3QEAXEA; hHeap
0x18000d048  call    cs:__imp_HeapAlloc
0x18000d04e  mov     rdi, rax
0x18000d051  test    rax, rax
0x18000d054  jz      short loc_18000D0AE
0x18000d056  mov     pdwClipSequenceNumber, [rsp+48h+stSize]; stSize
0x18000d05b  xor     ebx, ebx
0x18000d05d  mov     rdx, rsi; pClipFormatEtcDataArray
0x18000d060  mov     ppDataObj, rax; pFormatEtcDataArray
0x18000d063  lea     r9d, [rbx+1]; bCheckAvailable
0x18000d067  call    ?CopyFormatEtcDataArray@@YAXPEAUFORMATETCDATAARRAY@@0_KH@Z; CopyFormatEtcDataArray(FORMATETCDATAARRAY *,FORMATETCDATAARRAY *,unsigned __int64,int)
0x18000d06c  mov     ppDataObj, rbp; hMem
0x18000d06f  call    cs:__imp_GlobalUnlock
0x18000d075  test    ebx, ebx
0x18000d077  js      loc_18000D0FF
0x18000d07d  mov     edx, r12d; createClipDataObjectOptions
0x18000d080  mov     pdwClipSequenceNumber, r15; ppDataObj
0x18000d083  mov     ppDataObj, rdi; pFormatEtcDataArray
0x18000d086  call    ?Create@CClipDataObject@@SAJPEAUFORMATETCDATAARRAY@@W4CreateClipDataObjectOptions@@PEAPEAUIDataObject@@@Z; CClipDataObject::Create(FORMATETCDATAARRAY *,CreateClipDataObjectOptions,IDataObject * *)
0x18000d08b  mov     ebx, eax
0x18000d08d  test    eax, eax
0x18000d08f  js      short loc_18000D0FF
0x18000d091  lea     ppDataObj, [rsp+48h+clipLock]; this
0x18000d096  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000d09b  mov     eax, ebx
0x18000d09d  mov     rbx, [rsp+48h+arg_8]
0x18000d0a2  add     rsp, 20h
0x18000d0a6  pop     r15
0x18000d0a8  pop     r12
0x18000d0aa  pop     rdi
0x18000d0ab  pop     rsi
0x18000d0ac  pop     rbp
0x18000d0ad  retn
0x18000d0ae  mov     ebx, 8007000Eh
0x18000d0b3  jmp     short loc_18000D06C
0x18000d0b5  xor     ecx, ecx; dwMilliseconds
0x18000d0b7  call    cs:__imp_Sleep
0x18000d0bd  mov     ppDataObj, rbx; hWndNewOwner
0x18000d0c0  call    cs:__imp_OpenClipboard
0x18000d0c6  test    eax, eax
0x18000d0c8  jnz     loc_18000CFB3
0x18000d0ce  mov     ebx, 800401D0h
0x18000d0d3  jmp     short loc_18000D091
0x18000d0d5  call    cs:__imp_GetLastError
0x18000d0db  mov     ebx, eax
0x18000d0dd  test    eax, eax
0x18000d0df  jle     short loc_18000D075
0x18000d0e1  movzx   ebx, ax
0x18000d0e4  or      ebx, 80070000h
0x18000d0ea  jmp     short loc_18000D075
0x18000d0ec  mov     ebx, 80004005h
0x18000d0f1  jmp     short loc_18000D091
0x18000d0f3  mov     ecx, edi; EvaluationDisabled
0x18000d0f5  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000d0fa  jmp     loc_18000CFC1
0x18000d0ff  test    rdi, rdi
0x18000d102  jz      short loc_18000D091
0x18000d104  mov     ppDataObj, cs:?g_hHeap@@3QEAXEA; hHeap
0x18000d10b  mov     pdwClipSequenceNumber, rdi; lpMem
0x18000d10e  xor     edx, edx; dwFlags
0x18000d110  call    cs:__imp_HeapFree
0x18000d116  jmp     loc_18000D091
```

# GetFileCorruptionEvent

- ea: `0x180002a88`
- end: `0x180002eff`
- name: `GetFileCorruptionEvent`
- size: `1143`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800038cc`

## callees

- `0x180002590`
- `0x180002a88`
- `0x180004f1c`
- `0x180007040`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180002ed3`
- `KERNEL32!HeapFree` at `0x180002ed3`
- `KERNEL32!GetLastError` at `0x180002c6d`
- `KERNEL32!GetLastError` at `0x180002c6d`
- `KERNEL32!HeapAlloc` at `0x180002b22`
- `KERNEL32!HeapAlloc` at `0x180002ba5`
- `KERNEL32!HeapAlloc` at `0x180002cca`
- `KERNEL32!HeapAlloc` at `0x180002d91`
- `KERNEL32!HeapAlloc` at `0x180002b22`
- `KERNEL32!HeapAlloc` at `0x180002ba5`
- `KERNEL32!HeapAlloc` at `0x180002cca`
- `KERNEL32!HeapAlloc` at `0x180002d91`
- `KERNEL32!GetProcessHeap` at `0x180002b14`
- `KERNEL32!GetProcessHeap` at `0x180002b97`
- `KERNEL32!GetProcessHeap` at `0x180002cbc`
- `KERNEL32!GetProcessHeap` at `0x180002d83`
- `KERNEL32!GetProcessHeap` at `0x180002ec5`
- `KERNEL32!GetProcessHeap` at `0x180002b14`
- `KERNEL32!GetProcessHeap` at `0x180002b97`
- `KERNEL32!GetProcessHeap` at `0x180002cbc`
- `KERNEL32!GetProcessHeap` at `0x180002d83`
- `KERNEL32!GetProcessHeap` at `0x180002ec5`
- `ADVAPI32!CopySid` at `0x180002bca`
- `ADVAPI32!CopySid` at `0x180002bca`
- `wdi!WdiGetEvent` at `0x180002af9`
- `wdi!WdiGetEvent` at `0x180002b4d`
- `wdi!WdiGetEvent` at `0x180002af9`
- `wdi!WdiGetEvent` at `0x180002b4d`
- `tdh!TdhGetProperty` at `0x180002d08`
- `tdh!TdhGetProperty` at `0x180002dd0`
- `tdh!TdhGetProperty` at `0x180002e29`
- `tdh!TdhGetProperty` at `0x180002e7a`
- `tdh!TdhGetProperty` at `0x180002d08`
- `tdh!TdhGetProperty` at `0x180002dd0`
- `tdh!TdhGetProperty` at `0x180002e29`
- `tdh!TdhGetProperty` at `0x180002e7a`
- `tdh!TdhGetPropertySize` at `0x180002c5d`
- `tdh!TdhGetPropertySize` at `0x180002d58`
- `tdh!TdhGetPropertySize` at `0x180002c5d`
- `tdh!TdhGetPropertySize` at `0x180002d58`

## string_xrefs

- `0x180002ad7`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x180002eb9`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x180002c27`: `CorruptedFilePath`

## pseudocode

```c
__int64 __fastcall GetFileCorruptionEvent(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  int Event; // eax
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  struct _EVENT_RECORD *v8; // rax
  struct _EVENT_RECORD *v9; // rsi
  int v10; // eax
  int v11; // r9d
  int v12; // edx
  int v13; // r13d
  int v14; // r12d
  PEVENT_HEADER_EXTENDED_DATA_ITEM ExtendedData; // rax
  unsigned int DataSize; // ebx
  HANDLE v17; // rax
  void *v18; // rax
  PEVENT_HEADER_EXTENDED_DATA_ITEM v19; // rax
  signed int PropertySize; // eax
  signed int LastError; // eax
  ULONG v22; // ebx
  HANDLE v23; // rax
  BYTE *pBuffer; // rax
  signed int Property; // eax
  signed int v26; // eax
  ULONG v27; // ebx
  HANDLE v28; // rax
  BYTE *v29; // rax
  signed int v30; // eax
  signed int v31; // eax
  signed int v32; // eax
  HANDLE v33; // rax
  ULONG BufferSize; // [rsp+40h] [rbp-20h] BYREF
  unsigned int dwBytes; // [rsp+44h] [rbp-1Ch] BYREF
  PROPERTY_DATA_DESCRIPTOR dwBytes_4; // [rsp+48h] [rbp-18h] BYREF

  dwBytes = 0;
  if ( a2 )
  {
    CrashEventData::Free((CrashEventData *)a2);
    Event = WdiGetEvent(a1, 0, &dwBytes);
    v4 = Event;
    if ( Event < 0 )
    {
      DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 651, Event);
      return v4;
    }
    v6 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v8 = (struct _EVENT_RECORD *)HeapAlloc(ProcessHeap, 0, v6);
    v9 = v8;
    if ( !v8 )
    {
      v4 = -2147024882;
      DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 654, -2147024882);
      return v4;
    }
    v10 = WdiGetEvent(a1, v8, &dwBytes);
    v4 = v10;
    if ( v10 >= 0 )
    {
      if ( v9->ExtendedDataCount >= 2u )
      {
        v12 = 0;
        v13 = 0;
        v14 = 0;
        do
        {
          ExtendedData = v9->ExtendedData;
          if ( ExtendedData[v14].ExtType == 2 )
          {
            DataSize = ExtendedData[v14].DataSize;
            v17 = GetProcessHeap();
            v18 = HeapAlloc(v17, 0, DataSize);
            *(_QWORD *)(a2 + 24) = v18;
            if ( !v18 )
            {
              v10 = -2147024882;
              v11 = 673;
              goto LABEL_61;
            }
            if ( !CopySid(v9->ExtendedData[v14].DataSize, v18, (PSID)v9->ExtendedData[v14].DataPtr) )
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError > 0 )
                v4 = (unsigned __int16)LastError | 0x80070000;
              DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 675, v4);
              goto LABEL_63;
            }
            v12 = 1;
          }
          v19 = v9->ExtendedData;
          if ( v19[v14].ExtType == 3 )
          {
            v13 = 1;
            *(_DWORD *)(a2 + 32) = *(_DWORD *)v19[v14].DataPtr;
          }
          ++v14;
        }
        while ( v14 < v9->ExtendedDataCount );
        if ( !v12 || !v13 )
        {
          v11 = 688;
          goto LABEL_60;
        }
        BufferSize = 0;
        dwBytes_4.PropertyName = (ULONGLONG)L"CorruptedFilePath";
        dwBytes_4.ArrayIndex = -1;
        PropertySize = TdhGetPropertySize(v9, 0, 0, 1u, &dwBytes_4, &BufferSize);
        if ( PropertySize )
        {
          if ( PropertySize > 0 )
            v4 = (unsigned __int16)PropertySize | 0x80070000;
          else
            v4 = PropertySize;
          DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 699, v4);
        }
        else
        {
          v22 = BufferSize;
          v23 = GetProcessHeap();
          pBuffer = (BYTE *)HeapAlloc(v23, 0, v22);
          *(_QWORD *)a2 = pBuffer;
          if ( !pBuffer )
          {
            v10 = -2147024882;
            v11 = 702;
            goto LABEL_61;
          }
          Property = TdhGetProperty(v9, 0, 0, 1u, &dwBytes_4, BufferSize, pBuffer);
          if ( Property )
          {
            if ( Property > 0 )
              v4 = (unsigned __int16)Property | 0x80070000;
            else
              v4 = Property;
            DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 711, v4);
          }
          else
          {
            dwBytes_4.PropertyName = (ULONGLONG)L"CrashedAppName";
            v26 = TdhGetPropertySize(v9, 0, 0, 1u, &dwBytes_4, &BufferSize);
            if ( v26 )
            {
              if ( v26 > 0 )
                v4 = (unsigned __int16)v26 | 0x80070000;
              else
                v4 = v26;
              DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 717, v4);
            }
            else
            {
              v27 = BufferSize;
              v28 = GetProcessHeap();
              v29 = (BYTE *)HeapAlloc(v28, 0, v27);
              *(_QWORD *)(a2 + 8) = v29;
              if ( !v29 )
              {
                v10 = -2147024882;
                v11 = 720;
                goto LABEL_61;
              }
              v30 = TdhGetProperty(v9, 0, 0, 1u, &dwBytes_4, BufferSize, v29);
              if ( v30 )
              {
                if ( v30 > 0 )
                  v4 = (unsigned __int16)v30 | 0x80070000;
                else
                  v4 = v30;
                DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 729, v4);
              }
              else
              {
                dwBytes_4.PropertyName = (ULONGLONG)L"ExceptionCode";
                v31 = TdhGetProperty(v9, 0, 0, 1u, &dwBytes_4, 4u, (PBYTE)(a2 + 16));
                if ( v31 )
                {
                  if ( v31 > 0 )
                    v4 = (unsigned __int16)v31 | 0x80070000;
                  else
                    v4 = v31;
                  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 741, v4);
                }
                else
                {
                  dwBytes_4.PropertyName = (ULONGLONG)L"ExceptionStatusCode";
                  v32 = TdhGetProperty(v9, 0, 0, 1u, &dwBytes_4, 4u, (PBYTE)(a2 + 20));
                  if ( v32 )
                  {
                    if ( v32 > 0 )
                      v4 = (unsigned __int16)v32 | 0x80070000;
                    else
                      v4 = v32;
                    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 752, v4);
                  }
                }
              }
            }
          }
        }
        goto LABEL_63;
      }
      v11 = 662;
LABEL_60:
      v10 = -2147418113;
LABEL_61:
      v4 = v10;
    }
    else
    {
      v11 = 657;
    }
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", v11, v10);
LABEL_63:
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v9);
    return v4;
  }
  v4 = -2147467259;
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetFileCorruptionEvent", 647, -2147467259);
  return v4;
}

```

## disassembly

```asm
0x180002a88  mov     [rsp-38h+arg_10], rbx
0x180002a8d  push    rbp
0x180002a8e  push    rsi
0x180002a8f  push    rdi
0x180002a90  push    r12
0x180002a92  push    r13
0x180002a94  push    r14
0x180002a96  push    r15
0x180002a98  mov     rbp, rsp
0x180002a9b  sub     rsp, 60h
0x180002a9f  mov     rax, cs:__security_cookie
0x180002aa6  xor     rax, rsp
0x180002aa9  mov     [rbp+var_8], rax
0x180002aad  mov     dword ptr [rbp+dwBytes], 0
0x180002ab4  mov     r14, rdx
0x180002ab7  mov     r15, rcx
0x180002aba  test    rdx, rdx
0x180002abd  jnz     short loc_180002AE8
0x180002abf  mov     edi, 80004005h
0x180002ac4  mov     r9d, 287h
0x180002aca  mov     dword ptr [rsp+60h+pPropertyData], edi
0x180002ace  lea     r8, aGetfilecorrupt; "GetFileCorruptionEvent"
0x180002ad5  xor     ecx, ecx; Level
0x180002ad7  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180002ade  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180002ae3  jmp     loc_180002ED9
0x180002ae8  mov     rcx, r14; this
0x180002aeb  call    ?Free@CrashEventData@@QEAAXXZ; CrashEventData::Free(void)
0x180002af0  lea     r8, [rbp+dwBytes]
0x180002af4  xor     edx, edx
0x180002af6  mov     rcx, r15
0x180002af9  call    cs:__imp_WdiGetEvent
0x180002aff  mov     edi, eax
0x180002b01  test    eax, eax
0x180002b03  jns     short loc_180002B11
0x180002b05  mov     dword ptr [rsp+60h+pPropertyData], eax
0x180002b09  mov     r9d, 28Bh
0x180002b0f  jmp     short loc_180002ACE
0x180002b11  mov     ebx, dword ptr [rbp+dwBytes]
0x180002b14  call    cs:__imp_GetProcessHeap
0x180002b1a  mov     r8d, ebx; dwBytes
0x180002b1d  xor     edx, edx; dwFlags
0x180002b1f  mov     rcx, rax; hHeap
0x180002b22  call    cs:__imp_HeapAlloc
0x180002b28  mov     rsi, rax
0x180002b2b  test    rax, rax
0x180002b2e  jnz     short loc_180002B43
0x180002b30  mov     eax, 8007000Eh
0x180002b35  mov     r9d, 28Eh
0x180002b3b  mov     edi, eax
0x180002b3d  mov     dword ptr [rsp+60h+pPropertyData], eax
0x180002b41  jmp     short loc_180002ACE
0x180002b43  lea     r8, [rbp+dwBytes]
0x180002b47  mov     rdx, rsi
0x180002b4a  mov     rcx, r15
0x180002b4d  call    cs:__imp_WdiGetEvent
0x180002b53  mov     edi, eax
0x180002b55  test    eax, eax
0x180002b57  jns     short loc_180002B64
0x180002b59  mov     r9d, 291h
0x180002b5f  jmp     loc_180002EAC
0x180002b64  cmp     word ptr [rsi+54h], 2
0x180002b69  jnb     short loc_180002B76
0x180002b6b  mov     r9d, 296h
0x180002b71  jmp     loc_180002EA5
0x180002b76  xor     edx, edx
0x180002b78  xor     r13d, r13d
0x180002b7b  xor     r12d, r12d
0x180002b7e  mov     rax, [rsi+58h]
0x180002b82  movsxd  r15, r12d
0x180002b85  add     r15, r15
0x180002b88  cmp     word ptr [rax+r15*8+2], 2
0x180002b8f  jnz     short loc_180002BDD
0x180002b91  movzx   ebx, word ptr [rax+r15*8+6]
0x180002b97  call    cs:__imp_GetProcessHeap
0x180002b9d  mov     r8d, ebx; dwBytes
0x180002ba0  xor     edx, edx; dwFlags
0x180002ba2  mov     rcx, rax; hHeap
0x180002ba5  call    cs:__imp_HeapAlloc
0x180002bab  mov     [r14+18h], rax
0x180002baf  test    rax, rax
0x180002bb2  jz      loc_180002C91
0x180002bb8  mov     r8, [rsi+58h]
0x180002bbc  mov     rdx, rax; pDestinationSid
0x180002bbf  movzx   ecx, word ptr [r8+r15*8+6]; nDestinationSidLength
0x180002bc5  mov     r8, [r8+r15*8+8]; pSourceSid
0x180002bca  call    cs:__imp_CopySid
0x180002bd0  test    eax, eax
0x180002bd2  jz      loc_180002C6D
0x180002bd8  mov     edx, 1
0x180002bdd  mov     rax, [rsi+58h]
0x180002be1  cmp     word ptr [rax+r15*8+2], 3
0x180002be8  jnz     short loc_180002C00
0x180002bea  mov     rax, [rax+r15*8+8]
0x180002bef  mov     r15d, 1
0x180002bf5  mov     r13d, r15d
0x180002bf8  mov     ecx, [rax]
0x180002bfa  mov     [r14+20h], ecx
0x180002bfe  jmp     short loc_180002C06
0x180002c00  mov     r15d, 1
0x180002c06  movzx   eax, word ptr [rsi+54h]
0x180002c0a  add     r12d, r15d
0x180002c0d  cmp     r12d, eax
0x180002c10  jl      loc_180002B7E
0x180002c16  test    edx, edx
0x180002c18  jz      loc_180002E9F
0x180002c1e  test    r13d, r13d
0x180002c21  jz      loc_180002E9F
0x180002c27  lea     rax, aCorruptedfilep; "CorruptedFilePath"
0x180002c2e  mov     [rbp+BufferSize], 0
0x180002c35  mov     [rbp+dwBytes+4], rax
0x180002c39  mov     r9d, r15d; PropertyDataCount
0x180002c3c  lea     rax, [rbp+BufferSize]
0x180002c40  mov     [rbp+var_10], 0FFFFFFFFh
0x180002c47  mov     [rsp+60h+pPropertySize], rax; pPropertySize
0x180002c4c  xor     r8d, r8d; pTdhContext
0x180002c4f  lea     rax, [rbp+dwBytes+4]
0x180002c53  xor     edx, edx; TdhContextCount
0x180002c55  mov     rcx, rsi; pEvent
0x180002c58  mov     [rsp+60h+pPropertyData], rax; pPropertyData
0x180002c5d  call    cs:__imp_TdhGetPropertySize
0x180002c63  test    eax, eax
0x180002c65  jz      short loc_180002CB9
0x180002c67  jg      short loc_180002CA1
0x180002c69  mov     edi, eax
0x180002c6b  jmp     short loc_180002CAA
0x180002c6d  call    cs:__imp_GetLastError
0x180002c73  mov     edi, eax
0x180002c75  test    eax, eax
0x180002c77  jle     short loc_180002C82
0x180002c79  movzx   edi, ax
0x180002c7c  or      edi, 80070000h
0x180002c82  mov     dword ptr [rsp+60h+pPropertyData], edi
0x180002c86  mov     r9d, 2A3h
0x180002c8c  jmp     loc_180002EB0
0x180002c91  mov     eax, 8007000Eh
0x180002c96  mov     r9d, 2A1h
0x180002c9c  jmp     loc_180002EAA
0x180002ca1  movzx   edi, ax
0x180002ca4  or      edi, 80070000h
0x180002caa  mov     dword ptr [rsp+60h+pPropertyData], edi
0x180002cae  mov     r9d, 2BBh
0x180002cb4  jmp     loc_180002EB0
0x180002cb9  mov     ebx, [rbp+BufferSize]
0x180002cbc  call    cs:__imp_GetProcessHeap
0x180002cc2  mov     r8d, ebx; dwBytes
0x180002cc5  xor     edx, edx; dwFlags
0x180002cc7  mov     rcx, rax; hHeap
0x180002cca  call    cs:__imp_HeapAlloc
0x180002cd0  mov     [r14], rax
0x180002cd3  test    rax, rax
0x180002cd6  jnz     short loc_180002CE8
0x180002cd8  mov     eax, 8007000Eh
0x180002cdd  mov     r9d, 2BEh
0x180002ce3  jmp     loc_180002EAA
0x180002ce8  mov     [rsp+60h+pBuffer], rax; pBuffer
0x180002ced  mov     r9d, r15d; PropertyDataCount
0x180002cf0  mov     eax, [rbp+BufferSize]
0x180002cf3  xor     r8d, r8d; pTdhContext
0x180002cf6  mov     dword ptr [rsp+60h+pPropertySize], eax; BufferSize
0x180002cfa  xor     edx, edx; TdhContextCount
0x180002cfc  lea     rax, [rbp+dwBytes+4]
0x180002d00  mov     rcx, rsi; pEvent
0x180002d03  mov     [rsp+60h+pPropertyData], rax; pPropertyData
0x180002d08  call    cs:__imp_TdhGetProperty
0x180002d0e  test    eax, eax
0x180002d10  jz      short loc_180002D30
0x180002d12  jg      short loc_180002D18
0x180002d14  mov     edi, eax
0x180002d16  jmp     short loc_180002D21
0x180002d18  movzx   edi, ax
0x180002d1b  or      edi, 80070000h
0x180002d21  mov     dword ptr [rsp+60h+pPropertyData], edi
0x180002d25  mov     r9d, 2C7h
0x180002d2b  jmp     loc_180002EB0
0x180002d30  lea     rax, aCrashedappname; "CrashedAppName"
0x180002d37  mov     r9d, r15d; PropertyDataCount
0x180002d3a  mov     [rbp+dwBytes+4], rax
0x180002d3e  xor     r8d, r8d; pTdhContext
0x180002d41  lea     rax, [rbp+BufferSize]
0x180002d45  xor     edx, edx; TdhContextCount
0x180002d47  mov     [rsp+60h+pPropertySize], rax; pPropertySize
0x180002d4c  mov     rcx, rsi; pEvent
0x180002d4f  lea     rax, [rbp+dwBytes+4]
0x180002d53  mov     [rsp+60h+pPropertyData], rax; pPropertyData
0x180002d58  call    cs:__imp_TdhGetPropertySize
0x180002d5e  test    eax, eax
0x180002d60  jz      short loc_180002D80
0x180002d62  jg      short loc_180002D68
0x180002d64  mov     edi, eax
0x180002d66  jmp     short loc_180002D71
0x180002d68  movzx   edi, ax
0x180002d6b  or      edi, 80070000h
0x180002d71  mov     dword ptr [rsp+60h+pPropertyData], edi
0x180002d75  mov     r9d, 2CDh
0x180002d7b  jmp     loc_180002EB0
0x180002d80  mov     ebx, [rbp+BufferSize]
0x180002d83  call    cs:__imp_GetProcessHeap
0x180002d89  mov     r8d, ebx; dwBytes
0x180002d8c  xor     edx, edx; dwFlags
0x180002d8e  mov     rcx, rax; hHeap
0x180002d91  call    cs:__imp_HeapAlloc
0x180002d97  mov     [r14+8], rax
0x180002d9b  test    rax, rax
0x180002d9e  jnz     short loc_180002DB0
0x180002da0  mov     eax, 8007000Eh
0x180002da5  mov     r9d, 2D0h
0x180002dab  jmp     loc_180002EAA
0x180002db0  mov     [rsp+60h+pBuffer], rax; pBuffer
0x180002db5  mov     r9d, r15d; PropertyDataCount
0x180002db8  mov     eax, [rbp+BufferSize]
0x180002dbb  xor     r8d, r8d; pTdhContext
0x180002dbe  mov     dword ptr [rsp+60h+pPropertySize], eax; BufferSize
0x180002dc2  xor     edx, edx; TdhContextCount
0x180002dc4  lea     rax, [rbp+dwBytes+4]
0x180002dc8  mov     rcx, rsi; pEvent
0x180002dcb  mov     [rsp+60h+pPropertyData], rax; pPropertyData
0x180002dd0  call    cs:__imp_TdhGetProperty
0x180002dd6  test    eax, eax
0x180002dd8  jz      short loc_180002DF8
0x180002dda  jg      short loc_180002DE0
0x180002ddc  mov     edi, eax
0x180002dde  jmp     short loc_180002DE9
0x180002de0  movzx   edi, ax
0x180002de3  or      edi, 80070000h
0x180002de9  mov     dword ptr [rsp+60h+pPropertyData], edi
0x180002ded  mov     r9d, 2D9h
0x180002df3  jmp     loc_180002EB0
0x180002df8  lea     rax, aExceptioncode; "ExceptionCode"
0x180002dff  mov     ebx, 4
0x180002e04  mov     [rbp+dwBytes+4], rax
0x180002e08  mov     r9d, r15d; PropertyDataCount
0x180002e0b  lea     rax, [r14+10h]
0x180002e0f  xor     r8d, r8d; pTdhContext
0x180002e12  mov     [rsp+60h+pBuffer], rax; pBuffer
0x180002e17  xor     edx, edx; TdhContextCount
0x180002e19  lea     rax, [rbp+dwBytes+4]
0x180002e1d  mov     dword ptr [rsp+60h+pPropertySize], ebx; BufferSize
0x180002e21  mov     rcx, rsi; pEvent
0x180002e24  mov     [rsp+60h+pPropertyData], rax; pPropertyData
0x180002e29  call    cs:__imp_TdhGetProperty
0x180002e2f  test    eax, eax
0x180002e31  jz      short loc_180002E4E
0x180002e33  jg      short loc_180002E39
0x180002e35  mov     edi, eax
0x180002e37  jmp     short loc_180002E42
0x180002e39  movzx   edi, ax
0x180002e3c  or      edi, 80070000h
0x180002e42  mov     dword ptr [rsp+60h+pPropertyData], edi
0x180002e46  mov     r9d, 2E5h
0x180002e4c  jmp     short loc_180002EB0
0x180002e4e  lea     rax, aExceptionstatu; "ExceptionStatusCode"
0x180002e55  mov     r9d, r15d; PropertyDataCount
0x180002e58  mov     [rbp+dwBytes+4], rax
0x180002e5c  xor     r8d, r8d; pTdhContext
0x180002e5f  lea     rax, [r14+14h]
0x180002e63  xor     edx, edx; TdhContextCount
0x180002e65  mov     [rsp+60h+pBuffer], rax; pBuffer
0x180002e6a  mov     rcx, rsi; pEvent
0x180002e6d  lea     rax, [rbp+dwBytes+4]
0x180002e71  mov     dword ptr [rsp+60h+pPropertySize], ebx; BufferSize
0x180002e75  mov     [rsp+60h+pPropertyData], rax; pPropertyData
0x180002e7a  call    cs:__imp_TdhGetProperty
0x180002e80  test    eax, eax
0x180002e82  jz      short loc_180002EC5
0x180002e84  jg      short loc_180002E8A
0x180002e86  mov     edi, eax
0x180002e88  jmp     short loc_180002E93
0x180002e8a  movzx   edi, ax
0x180002e8d  or      edi, 80070000h
0x180002e93  mov     dword ptr [rsp+60h+pPropertyData], edi
0x180002e97  mov     r9d, 2F0h
0x180002e9d  jmp     short loc_180002EB0
0x180002e9f  mov     r9d, 2B0h
0x180002ea5  mov     eax, 8000FFFFh
0x180002eaa  mov     edi, eax
0x180002eac  mov     dword ptr [rsp+60h+pPropertyData], eax
0x180002eb0  lea     r8, aGetfilecorrupt; "GetFileCorruptionEvent"
0x180002eb7  xor     ecx, ecx; Level
0x180002eb9  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180002ec0  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180002ec5  call    cs:__imp_GetProcessHeap
0x180002ecb  mov     r8, rsi; lpMem
0x180002ece  xor     edx, edx; dwFlags
0x180002ed0  mov     rcx, rax; hHeap
0x180002ed3  call    cs:__imp_HeapFree
0x180002ed9  mov     eax, edi
0x180002edb  mov     rcx, [rbp+var_8]
0x180002edf  xor     rcx, rsp; StackCookie
0x180002ee2  call    __security_check_cookie
0x180002ee7  mov     rbx, [rsp+60h+arg_10]
0x180002eef  add     rsp, 60h
0x180002ef3  pop     r15
0x180002ef5  pop     r14
0x180002ef7  pop     r13
0x180002ef9  pop     r12
0x180002efb  pop     rdi
0x180002efc  pop     rsi
0x180002efd  pop     rbp
0x180002efe  retn
  ... truncated ...
```

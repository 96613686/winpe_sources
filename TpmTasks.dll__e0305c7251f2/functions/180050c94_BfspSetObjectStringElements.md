# BfspSetObjectStringElements

- ea: `0x180050c94`
- end: `0x180050e6c`
- name: `BfspSetObjectStringElements`
- size: `472`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18004eb2c`
- `0x18004ed34`
- `0x18004ede8`

## callees

- `0x18004cdd4`
- `0x18004f888`
- `0x180050c94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050e3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050e3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050e2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050e2d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180050d99`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180050dcd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180050d99`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180050dcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050df7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050df7`
- `bcd!BcdSetElementData` at `0x180050deb`
- `bcd!BcdSetElementData` at `0x180050deb`
- `bcd!BcdCloseObject` at `0x180050e4a`
- `bcd!BcdCloseObject` at `0x180050e59`
- `bcd!BcdCloseObject` at `0x180050e4a`
- `bcd!BcdCloseObject` at `0x180050e59`
- `bcd!BcdOpenObject` at `0x180050cd9`
- `bcd!BcdOpenObject` at `0x180050d08`
- `bcd!BcdOpenObject` at `0x180050cd9`
- `bcd!BcdOpenObject` at `0x180050d08`

## string_xrefs

- `0x180050ce5`: `Failed to open a handle to the template store. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspSetObjectStringElements(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  int BcdElementData; // eax
  _DWORD *v10; // r14
  unsigned int v11; // edi
  int v12; // esi
  DWORD v13; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v16; // [rsp+40h] [rbp-30h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+50h] [rbp-20h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h] BYREF
  LPVOID lpMem[2]; // [rsp+60h] [rbp-10h] BYREF

  *(_QWORD *)Buffer = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  lpMem[0] = 0;
  v6 = BcdOpenObject(a1, a3, &v19);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = BcdOpenObject(a2, a4, &v18);
    v7 = v8;
    if ( v8 >= 0 )
    {
      BcdElementData = BfspGetBcdElementData(v19, 1191182341, lpMem, &v16);
      v10 = lpMem[0];
      v7 = BcdElementData;
      if ( BcdElementData >= 0 )
      {
        if ( (v16 & 0xF) != 0 )
        {
          v7 = -1073741811;
        }
        else
        {
          v11 = v16 >> 4;
          v12 = 0;
          if ( v16 >> 4 )
          {
            while ( 1 )
            {
              v13 = FormatMessageW(0xB00u, lpSource, v10[4 * v12 + 2], (unsigned __int16)word_1800A4540, Buffer, 0, 0);
              if ( !v13 )
              {
                v13 = FormatMessageW(0xB00u, lpSource, v10[4 * v12 + 2], 0, Buffer, 0, 0);
                if ( !v13 )
                {
                  v7 = -1073741823;
                  goto LABEL_17;
                }
              }
              v7 = BcdSetElementData(v18, (unsigned int)v10[4 * v12], *(_QWORD *)Buffer, 2 * v13 + 2);
              LocalFree(*(HLOCAL *)Buffer);
              if ( v7 < 0 )
                break;
              if ( ++v12 >= v11 )
                goto LABEL_17;
            }
            BfspLogMessage(4, L"Failed to set element description. Status = [%x]", (unsigned int)v7);
          }
        }
      }
LABEL_17:
      if ( v10 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v10);
      }
    }
    else
    {
      BfspLogMessage(4, L"Failed to get a handle to the system store. Status = [%x]", (unsigned int)v8);
    }
  }
  else
  {
    BfspLogMessage(4, L"Failed to open a handle to the template store. Status = [%x]", (unsigned int)v6);
  }
  if ( v18 )
    BcdCloseObject(v18);
  if ( v19 )
    BcdCloseObject(v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180050c94  push    rbp
0x180050c96  push    rbx
0x180050c97  push    rsi
0x180050c98  push    rdi
0x180050c99  push    r14
0x180050c9b  mov     rbp, rsp
0x180050c9e  sub     rsp, 70h
0x180050ca2  mov     rax, r8
0x180050ca5  mov     qword ptr [rbp+Buffer], 0
0x180050cad  mov     rsi, rdx
0x180050cb0  mov     [rbp+var_30], 0
0x180050cb7  mov     rdx, rax
0x180050cba  mov     [rbp+var_20], 0
0x180050cc2  lea     r8, [rbp+var_18]
0x180050cc6  mov     [rbp+var_18], 0
0x180050cce  mov     rdi, r9
0x180050cd1  mov     [rbp+lpMem], 0
0x180050cd9  call    cs:__imp_BcdOpenObject
0x180050cdf  mov     ebx, eax
0x180050ce1  test    eax, eax
0x180050ce3  jns     short loc_180050CFE
0x180050ce5  lea     rdx, aFailedToOpenAH_0; "Failed to open a handle to the template"...
0x180050cec  mov     r8d, eax
0x180050cef  mov     ecx, 4
0x180050cf4  call    BfspLogMessage
0x180050cf9  jmp     loc_180050E41
0x180050cfe  lea     r8, [rbp+var_20]
0x180050d02  mov     rdx, rdi
0x180050d05  mov     rcx, rsi
0x180050d08  call    cs:__imp_BcdOpenObject
0x180050d0e  mov     ebx, eax
0x180050d10  test    eax, eax
0x180050d12  jns     short loc_180050D1D
0x180050d14  lea     rdx, aFailedToGetAHa_0; "Failed to get a handle to the system st"...
0x180050d1b  jmp     short loc_180050CEC
0x180050d1d  mov     rcx, [rbp+var_18]
0x180050d21  lea     r9, [rbp+var_30]
0x180050d25  lea     r8, [rbp+lpMem]
0x180050d29  mov     edx, 47000005h
0x180050d2e  call    BfspGetBcdElementData
0x180050d33  mov     r14, [rbp+lpMem]
0x180050d37  mov     ebx, eax
0x180050d39  test    eax, eax
0x180050d3b  js      loc_180050E28
0x180050d41  mov     edi, [rbp+var_30]
0x180050d44  test    dil, 0Fh
0x180050d48  jz      short loc_180050D54
0x180050d4a  mov     ebx, 0C000000Dh
0x180050d4f  jmp     loc_180050E28
0x180050d54  shr     edi, 4
0x180050d57  xor     esi, esi
0x180050d59  test    edi, edi
0x180050d5b  jz      loc_180050E28
0x180050d61  movzx   r9d, cs:word_1800A4540; dwLanguageId
0x180050d69  lea     rax, [rbp+Buffer]
0x180050d6d  mov     rdx, cs:lpSource; lpSource
0x180050d74  mov     ecx, 0B00h; dwFlags
0x180050d79  mov     [rsp+70h+Arguments], 0; Arguments
0x180050d82  mov     ebx, esi
0x180050d84  add     rbx, rbx
0x180050d87  mov     [rsp+70h+nSize], 0; nSize
0x180050d8f  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x180050d94  mov     r8d, [r14+rbx*8+8]; dwMessageId
0x180050d99  call    cs:__imp_FormatMessageW
0x180050d9f  test    eax, eax
0x180050da1  jnz     short loc_180050DD7
0x180050da3  mov     r8d, [r14+rbx*8+8]; dwMessageId
0x180050da8  xor     r9d, r9d; dwLanguageId
0x180050dab  mov     rdx, cs:lpSource; lpSource
0x180050db2  mov     ecx, 0B00h; dwFlags
0x180050db7  mov     [rsp+70h+Arguments], 0; Arguments
0x180050dc0  mov     [rsp+70h+nSize], eax; nSize
0x180050dc4  lea     rax, [rbp+Buffer]
0x180050dc8  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x180050dcd  call    cs:__imp_FormatMessageW
0x180050dd3  test    eax, eax
0x180050dd5  jz      short loc_180050E0D
0x180050dd7  mov     r8, qword ptr [rbp+Buffer]
0x180050ddb  lea     r9d, ds:2[rax*2]
0x180050de3  mov     edx, [r14+rbx*8]
0x180050de7  mov     rcx, [rbp+var_20]
0x180050deb  call    cs:__imp_BcdSetElementData
0x180050df1  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x180050df5  mov     ebx, eax
0x180050df7  call    cs:__imp_LocalFree
0x180050dfd  test    ebx, ebx
0x180050dff  js      short loc_180050E14
0x180050e01  inc     esi
0x180050e03  cmp     esi, edi
0x180050e05  jb      loc_180050D61
0x180050e0b  jmp     short loc_180050E28
0x180050e0d  mov     ebx, 0C0000001h
0x180050e12  jmp     short loc_180050E28
0x180050e14  mov     r8d, ebx
0x180050e17  lea     rdx, aFailedToSetEle_0; "Failed to set element description. Stat"...
0x180050e1e  mov     ecx, 4
0x180050e23  call    BfspLogMessage
0x180050e28  test    r14, r14
0x180050e2b  jz      short loc_180050E41
0x180050e2d  call    cs:__imp_GetProcessHeap
0x180050e33  mov     r8, r14; lpMem
0x180050e36  xor     edx, edx; dwFlags
0x180050e38  mov     rcx, rax; hHeap
0x180050e3b  call    cs:__imp_HeapFree
0x180050e41  mov     rcx, [rbp+var_20]
0x180050e45  test    rcx, rcx
0x180050e48  jz      short loc_180050E50
0x180050e4a  call    cs:__imp_BcdCloseObject
0x180050e50  mov     rcx, [rbp+var_18]
0x180050e54  test    rcx, rcx
0x180050e57  jz      short loc_180050E5F
0x180050e59  call    cs:__imp_BcdCloseObject
0x180050e5f  mov     eax, ebx
0x180050e61  add     rsp, 70h
0x180050e65  pop     r14
0x180050e67  pop     rdi
0x180050e68  pop     rsi
0x180050e69  pop     rbx
0x180050e6a  pop     rbp
0x180050e6b  retn
```

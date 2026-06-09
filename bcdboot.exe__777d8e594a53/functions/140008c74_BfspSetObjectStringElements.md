# BfspSetObjectStringElements

- ea: `0x140008c74`
- end: `0x140008e61`
- name: `BfspSetObjectStringElements`
- size: `493`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1400058e4`
- `0x140005ae8`
- `0x140005b98`

## callees

- `0x140006a14`
- `0x140008c74`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x140018b54`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008e2e`
- `KERNEL32!HeapFree` at `0x140008e2e`
- `KERNEL32!FormatMessageW` at `0x140008d87`
- `KERNEL32!FormatMessageW` at `0x140008dbb`
- `KERNEL32!FormatMessageW` at `0x140008d87`
- `KERNEL32!FormatMessageW` at `0x140008dbb`
- `KERNEL32!GetProcessHeap` at `0x140008e20`
- `KERNEL32!GetProcessHeap` at `0x140008e20`
- `KERNEL32!LocalFree` at `0x140008dea`
- `KERNEL32!LocalFree` at `0x140008dea`

## string_xrefs

- `0x140008cc7`: `Failed to open a handle to the template store. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspSetObjectStringElements(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
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
  HANDLE Handle; // [rsp+50h] [rbp-20h] BYREF
  HANDLE v19; // [rsp+58h] [rbp-18h] BYREF
  LPVOID lpMem[2]; // [rsp+60h] [rbp-10h] BYREF

  *(_QWORD *)Buffer = 0;
  v16 = 0;
  Handle = 0;
  v19 = 0;
  lpMem[0] = 0;
  v6 = BcdOpenObject(a1, a3, &v19);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = BcdOpenObject(a2, a4, &Handle);
    v7 = v8;
    if ( v8 >= 0 )
    {
      BcdElementData = BfspGetBcdElementData((__int64)v19, 0x47000005u, lpMem, &v16);
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
              v13 = FormatMessageW(0xB00u, lpSource, v10[4 * v12 + 2], (unsigned __int16)word_14003F900, Buffer, 0, 0);
              if ( !v13 )
              {
                v13 = FormatMessageW(0xB00u, lpSource, v10[4 * v12 + 2], 0, Buffer, 0, 0);
                if ( !v13 )
                {
                  v7 = -1073741823;
                  goto LABEL_16;
                }
              }
              v7 = BcdSetElementDataWithFlags(
                     (__int64)Handle,
                     (unsigned int)v10[4 * v12],
                     0,
                     *(__int64 *)Buffer,
                     2 * v13 + 2);
              LocalFree(*(HLOCAL *)Buffer);
              if ( v7 < 0 )
                break;
              if ( ++v12 >= v11 )
                goto LABEL_16;
            }
            BfspLogMessage(4, L"Failed to set element description. Status = [%x]", (unsigned int)v7);
          }
        }
      }
LABEL_16:
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
    if ( Handle )
      BcdCloseObject(Handle);
  }
  else
  {
    BfspLogMessage(4, L"Failed to open a handle to the template store. Status = [%x]", (unsigned int)v6);
  }
  if ( v19 )
    BcdCloseObject(v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008c74  push    rbp
0x140008c76  push    rbx
0x140008c77  push    rsi
0x140008c78  push    rdi
0x140008c79  push    r14
0x140008c7b  mov     rbp, rsp
0x140008c7e  sub     rsp, 70h
0x140008c82  mov     rax, r8
0x140008c85  mov     qword ptr [rbp+Buffer], 0
0x140008c8d  mov     rsi, rdx
0x140008c90  mov     [rbp+var_30], 0
0x140008c97  mov     rdx, rax
0x140008c9a  mov     [rbp+Handle], 0
0x140008ca2  lea     r8, [rbp+var_18]
0x140008ca6  mov     [rbp+var_18], 0
0x140008cae  mov     rdi, r9
0x140008cb1  mov     [rbp+lpMem], 0
0x140008cb9  call    BcdOpenObject
0x140008cbe  mov     ebx, eax
0x140008cc0  test    eax, eax
0x140008cc2  jns     short loc_140008CDD
0x140008cc4  mov     r8d, eax
0x140008cc7  lea     rdx, aFailedToOpenAH_2; "Failed to open a handle to the template"...
0x140008cce  mov     ecx, 4
0x140008cd3  call    BfspLogMessage
0x140008cd8  jmp     loc_140008E44
0x140008cdd  lea     r8, [rbp+Handle]
0x140008ce1  mov     rdx, rdi
0x140008ce4  mov     rcx, rsi
0x140008ce7  call    BcdOpenObject
0x140008cec  mov     ebx, eax
0x140008cee  test    eax, eax
0x140008cf0  jns     short loc_140008D0B
0x140008cf2  mov     r8d, eax
0x140008cf5  lea     rdx, aFailedToGetAHa_0; "Failed to get a handle to the system st"...
0x140008cfc  mov     ecx, 4
0x140008d01  call    BfspLogMessage
0x140008d06  jmp     loc_140008E34
0x140008d0b  mov     rcx, [rbp+var_18]
0x140008d0f  lea     r9, [rbp+var_30]
0x140008d13  lea     r8, [rbp+lpMem]
0x140008d17  mov     edx, 47000005h
0x140008d1c  call    BfspGetBcdElementData
0x140008d21  mov     r14, [rbp+lpMem]
0x140008d25  mov     ebx, eax
0x140008d27  test    eax, eax
0x140008d29  js      loc_140008E1B
0x140008d2f  mov     edi, [rbp+var_30]
0x140008d32  test    dil, 0Fh
0x140008d36  jz      short loc_140008D42
0x140008d38  mov     ebx, 0C000000Dh
0x140008d3d  jmp     loc_140008E1B
0x140008d42  shr     edi, 4
0x140008d45  xor     esi, esi
0x140008d47  test    edi, edi
0x140008d49  jz      loc_140008E1B
0x140008d4f  movzx   r9d, cs:word_14003F900; dwLanguageId
0x140008d57  lea     rax, [rbp+Buffer]
0x140008d5b  mov     rdx, cs:lpSource; lpSource
0x140008d62  mov     ecx, 0B00h; dwFlags
0x140008d67  mov     [rsp+70h+Arguments], 0; Arguments
0x140008d70  mov     ebx, esi
0x140008d72  add     rbx, rbx
0x140008d75  mov     [rsp+70h+nSize], 0; nSize
0x140008d7d  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x140008d82  mov     r8d, [r14+rbx*8+8]; dwMessageId
0x140008d87  call    cs:__imp_FormatMessageW
0x140008d8d  test    eax, eax
0x140008d8f  jnz     short loc_140008DC5
0x140008d91  mov     r8d, [r14+rbx*8+8]; dwMessageId
0x140008d96  xor     r9d, r9d; dwLanguageId
0x140008d99  mov     rdx, cs:lpSource; lpSource
0x140008da0  mov     ecx, 0B00h; dwFlags
0x140008da5  mov     [rsp+70h+Arguments], 0; Arguments
0x140008dae  mov     [rsp+70h+nSize], eax; nSize
0x140008db2  lea     rax, [rbp+Buffer]
0x140008db6  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x140008dbb  call    cs:__imp_FormatMessageW
0x140008dc1  test    eax, eax
0x140008dc3  jz      short loc_140008E00
0x140008dc5  mov     r9, qword ptr [rbp+Buffer]
0x140008dc9  lea     eax, ds:2[rax*2]
0x140008dd0  mov     edx, [r14+rbx*8]
0x140008dd4  xor     r8d, r8d
0x140008dd7  mov     rcx, [rbp+Handle]
0x140008ddb  mov     dword ptr [rsp+70h+lpBuffer], eax
0x140008ddf  call    BcdSetElementDataWithFlags
0x140008de4  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x140008de8  mov     ebx, eax
0x140008dea  call    cs:__imp_LocalFree
0x140008df0  test    ebx, ebx
0x140008df2  js      short loc_140008E07
0x140008df4  inc     esi
0x140008df6  cmp     esi, edi
0x140008df8  jb      loc_140008D4F
0x140008dfe  jmp     short loc_140008E1B
0x140008e00  mov     ebx, 0C0000001h
0x140008e05  jmp     short loc_140008E1B
0x140008e07  mov     r8d, ebx
0x140008e0a  lea     rdx, aFailedToSetEle_0; "Failed to set element description. Stat"...
0x140008e11  mov     ecx, 4
0x140008e16  call    BfspLogMessage
0x140008e1b  test    r14, r14
0x140008e1e  jz      short loc_140008E34
0x140008e20  call    cs:__imp_GetProcessHeap
0x140008e26  mov     r8, r14; lpMem
0x140008e29  xor     edx, edx; dwFlags
0x140008e2b  mov     rcx, rax; hHeap
0x140008e2e  call    cs:__imp_HeapFree
0x140008e34  cmp     [rbp+Handle], 0
0x140008e39  jz      short loc_140008E44
0x140008e3b  mov     rcx, [rbp+Handle]; Handle
0x140008e3f  call    BcdCloseObject
0x140008e44  cmp     [rbp+var_18], 0
0x140008e49  jz      short loc_140008E54
0x140008e4b  mov     rcx, [rbp+var_18]; Handle
0x140008e4f  call    BcdCloseObject
0x140008e54  mov     eax, ebx
0x140008e56  add     rsp, 70h
0x140008e5a  pop     r14
0x140008e5c  pop     rdi
0x140008e5d  pop     rsi
0x140008e5e  pop     rbx
0x140008e5f  pop     rbp
0x140008e60  retn
```

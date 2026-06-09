# GetVolumeNameFromFilePath(ushort const *,ushort * *)

- ea: `0x180012ef4`
- end: `0x180013126`
- name: `?GetVolumeNameFromFilePath@@YAJPEBGPEAPEAG@Z`
- size: `562`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001441c`

## callees

- `0x1800124d8`
- `0x180012ef4`
- `0x18001312c`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013070`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013070`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013059`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800130f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013059`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800130f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013102`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130be`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800130b4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800130b4`

## pseudocode

```c
__int64 __fastcall GetVolumeNameFromFilePath(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  unsigned __int64 v6; // rdi
  int v7; // ecx
  HANDLE ProcessHeap; // rax
  unsigned int v9; // esi
  WCHAR *v10; // rax
  unsigned __int16 *v11; // rdi
  signed int LastError; // eax
  HANDLE v13; // rax
  SIZE_T dwBytes; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int64 v16; // [rsp+88h] [rbp+20h] BYREF

  v16 = 0;
  LODWORD(dwBytes) = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 4, 144);
  v4 = StringCbLengthW(a1, 0xFFFFFFFE, &v16);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v4,
              4,
              144) >= 0 )
  {
    fnEfsLogTrace1Strings(v5, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 4, 146);
    v6 = -1;
    if ( v16 + 2 >= v16 )
      v6 = v16 + 2;
    v4 = v16 + 2 < v16 ? 0x80070216 : 0;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v4,
                4,
                146) >= 0 )
    {
      fnEfsLogTrace1Strings(v7, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 4, 148);
      v4 = ULongLongToULong(v6, (unsigned int *)&dwBytes);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v4,
                  4,
                  148) >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v9 = dwBytes;
        v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, (unsigned int)dwBytes);
        v11 = v10;
        if ( v10 )
        {
          if ( GetVolumePathNameW(a1, v10, v9 >> 1) )
          {
            *a2 = v11;
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v4, 4, 155);
            v13 = GetProcessHeap();
            HeapFree(v13, 0, v11);
          }
        }
        else
        {
          v4 = -2147024882;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 4, 151);
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180012ef4  mov     rax, rsp
0x180012ef7  mov     [rax+8], rbx
0x180012efb  mov     [rax+10h], rbp
0x180012eff  push    rsi
0x180012f00  push    rdi
0x180012f01  push    r12
0x180012f03  push    r14
0x180012f05  push    r15
0x180012f07  sub     rsp, 40h
0x180012f0b  mov     r14, rdx
0x180012f0e  mov     qword ptr [rax+20h], 0
0x180012f16  mov     r15d, 4
0x180012f1c  mov     dword ptr [rax+18h], 0
0x180012f23  lea     r12, sourceString
0x180012f2a  mov     edi, 0B90h
0x180012f2f  mov     r9d, r15d
0x180012f32  mov     [rax-48h], edi
0x180012f35  mov     r8, r12
0x180012f38  lea     rdx, EFS_TRACE_START_EVENT
0x180012f3f  mov     rbp, rcx
0x180012f42  call    fnEfsLogTrace1Strings
0x180012f47  lea     r8, [rsp+68h+arg_18]; unsigned __int64 *
0x180012f4f  mov     edx, 0FFFFFFFEh; unsigned __int64
0x180012f54  mov     rcx, rbp; unsigned __int16 *
0x180012f57  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180012f5c  mov     rcx, cs:g_hPublisher
0x180012f63  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180012f6a  mov     [rsp+68h+var_38], edi
0x180012f6e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180012f75  mov     [rsp+68h+var_40], r15d
0x180012f7a  mov     r9, r12
0x180012f7d  mov     [rsp+68h+var_48], eax
0x180012f81  mov     ebx, eax
0x180012f83  call    fnEfsLogTrace1String1Dword
0x180012f88  test    eax, eax
0x180012f8a  js      loc_18001310D
0x180012f90  lea     esi, [rdi+2]
0x180012f93  mov     r9d, r15d
0x180012f96  mov     r8, r12
0x180012f99  mov     [rsp+68h+var_48], esi
0x180012f9d  lea     rdx, EFS_TRACE_START_EVENT
0x180012fa4  call    fnEfsLogTrace1Strings
0x180012fa9  mov     rcx, [rsp+68h+arg_18]
0x180012fb1  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180012fb8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180012fbc  mov     [rsp+68h+var_38], esi
0x180012fc0  mov     [rsp+68h+var_40], r15d
0x180012fc5  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180012fcc  mov     r9, r12
0x180012fcf  lea     rax, [rcx+2]
0x180012fd3  cmp     rax, rcx
0x180012fd6  mov     rcx, cs:g_hPublisher
0x180012fdd  cmovnb  rdi, rax
0x180012fe1  sbb     ebx, ebx
0x180012fe3  and     ebx, 80070216h
0x180012fe9  mov     [rsp+68h+var_48], ebx
0x180012fed  call    fnEfsLogTrace1String1Dword
0x180012ff2  test    eax, eax
0x180012ff4  js      loc_18001310D
0x180012ffa  mov     esi, 0B94h
0x180012fff  lea     rdx, EFS_TRACE_START_EVENT
0x180013006  mov     r9d, r15d
0x180013009  mov     [rsp+68h+var_48], esi
0x18001300d  mov     r8, r12
0x180013010  call    fnEfsLogTrace1Strings
0x180013015  lea     rdx, [rsp+68h+dwBytes]; unsigned int *
0x18001301d  mov     rcx, rdi; unsigned __int64
0x180013020  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180013025  mov     rcx, cs:g_hPublisher
0x18001302c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180013033  mov     [rsp+68h+var_38], esi
0x180013037  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18001303e  mov     [rsp+68h+var_40], r15d
0x180013043  mov     r9, r12
0x180013046  mov     [rsp+68h+var_48], eax
0x18001304a  mov     ebx, eax
0x18001304c  call    fnEfsLogTrace1String1Dword
0x180013051  test    eax, eax
0x180013053  js      loc_18001310D
0x180013059  call    cs:__imp_GetProcessHeap
0x18001305f  mov     esi, dword ptr [rsp+68h+dwBytes]
0x180013066  lea     edx, [r15+4]; dwFlags
0x18001306a  mov     r8d, esi; dwBytes
0x18001306d  mov     rcx, rax; hHeap
0x180013070  call    cs:__imp_HeapAlloc
0x180013076  mov     rdi, rax
0x180013079  test    rax, rax
0x18001307c  jnz     short loc_1800130A9
0x18001307e  mov     rcx, cs:g_hPublisher
0x180013085  lea     rdx, EFS_TRACE_ERROR
0x18001308c  mov     r9d, r15d
0x18001308f  mov     [rsp+68h+var_48], 0B97h
0x180013097  mov     r8d, 8007000Eh
0x18001309d  mov     ebx, 8007000Eh
0x1800130a2  call    fnEfsLogTrace1
0x1800130a7  jmp     short loc_18001310D
0x1800130a9  shr     esi, 1
0x1800130ab  mov     rdx, rdi; lpszVolumePathName
0x1800130ae  mov     r8d, esi; cchBufferLength
0x1800130b1  mov     rcx, rbp; lpszFileName
0x1800130b4  call    cs:__imp_GetVolumePathNameW
0x1800130ba  test    eax, eax
0x1800130bc  jnz     short loc_18001310A
0x1800130be  call    cs:__imp_GetLastError
0x1800130c4  mov     ebx, eax
0x1800130c6  test    eax, eax
0x1800130c8  jle     short loc_1800130D3
0x1800130ca  movzx   ebx, ax
0x1800130cd  or      ebx, 80070000h
0x1800130d3  mov     rcx, cs:g_hPublisher
0x1800130da  lea     rdx, EFS_TRACE_ERROR
0x1800130e1  mov     r9d, r15d
0x1800130e4  mov     [rsp+68h+var_48], 0B9Bh
0x1800130ec  mov     r8d, ebx
0x1800130ef  call    fnEfsLogTrace1
0x1800130f4  call    cs:__imp_GetProcessHeap
0x1800130fa  mov     r8, rdi; lpMem
0x1800130fd  xor     edx, edx; dwFlags
0x1800130ff  mov     rcx, rax; hHeap
0x180013102  call    cs:__imp_HeapFree
0x180013108  jmp     short loc_18001310D
0x18001310a  mov     [r14], rdi
0x18001310d  mov     rbp, [rsp+68h+arg_8]
0x180013112  mov     eax, ebx
0x180013114  mov     rbx, [rsp+68h+arg_0]
0x180013119  add     rsp, 40h
0x18001311d  pop     r15
0x18001311f  pop     r14
0x180013121  pop     r12
0x180013123  pop     rdi
0x180013124  pop     rsi
0x180013125  retn
```

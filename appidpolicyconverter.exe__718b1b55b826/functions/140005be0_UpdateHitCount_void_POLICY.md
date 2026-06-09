# UpdateHitCount(void *,_POLICY *)

- ea: `0x140005be0`
- end: `0x140005eb5`
- name: `?UpdateHitCount@@YAKPEAXPEAU_POLICY@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(HANDLE hDevice, struct _POLICY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000458c`

## callees

- `0x140001b98`
- `0x140005a50`
- `0x140005be0`
- `0x140008d30`
- `0x140008ef4`
- `0x140013ab7`
- `0x140013b10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140005c27`
- `msvcrt!_wcsicmp` at `0x140005c3b`
- `msvcrt!_wcsicmp` at `0x140005e39`
- `msvcrt!_wcsicmp` at `0x140005c27`
- `msvcrt!_wcsicmp` at `0x140005c3b`
- `msvcrt!_wcsicmp` at `0x140005e39`
- `msvcrt!qsort` at `0x140005dad`
- `msvcrt!qsort` at `0x140005dc6`
- `msvcrt!qsort` at `0x140005dad`
- `msvcrt!qsort` at `0x140005dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e98`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140005c9a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140005c9a`
- `ntdll!EtwEventWrite` at `0x140005d94`
- `ntdll!EtwEventWrite` at `0x140005e8d`
- `ntdll!EtwEventWrite` at `0x140005d94`
- `ntdll!EtwEventWrite` at `0x140005e8d`

## pseudocode

```c
__int64 __fastcall UpdateHitCount(HANDLE hDevice, struct _POLICY *a2)
{
  DWORD LastError; // edi
  unsigned int *v5; // r14
  unsigned __int16 *lpOutBuffer; // rbx
  __int64 nOutBufferSize; // rbp
  unsigned __int16 *i; // rcx
  unsigned __int16 *v9; // rax
  unsigned int v11; // r8d
  _DWORD *v12; // r12
  int v13; // edx
  unsigned int j; // edx
  unsigned int v15; // r15d
  unsigned int k; // ebp
  __int64 v17; // r13
  unsigned __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-258h] BYREF
  wchar_t String1[256]; // [rsp+50h] [rbp-248h] BYREF

  BytesReturned[0] = 0;
  LastError = 0;
  v5 = 0;
  if ( _wcsicmp(*(const wchar_t **)a2, L"EXE") && _wcsicmp(*(const wchar_t **)a2, L"DLL") )
  {
    lpOutBuffer = 0;
  }
  else
  {
    nOutBufferSize = 4096;
    for ( i = 0; ; i = lpOutBuffer )
    {
      AiFree(i);
      v9 = (unsigned __int16 *)AiAlloc(nOutBufferSize);
      lpOutBuffer = v9;
      if ( !v9 )
        goto LABEL_10;
      if ( (int)StringCbCopyW(v9, 0x10u, *(size_t **)a2) < 0 )
      {
        LastError = 87;
        goto LABEL_11;
      }
      *((_DWORD *)lpOutBuffer + 4) = nOutBufferSize;
      if ( !DeviceIoControl(hDevice, 0x229808u, lpOutBuffer, 0x24u, lpOutBuffer, nOutBufferSize, BytesReturned, 0) )
      {
        LastError = GetLastError();
        goto LABEL_11;
      }
      if ( *((_DWORD *)lpOutBuffer + 4) <= (unsigned int)nOutBufferSize )
        break;
      nOutBufferSize = *((unsigned int *)lpOutBuffer + 4);
    }
    v11 = *((_DWORD *)lpOutBuffer + 5);
    if ( v11 )
    {
      v12 = lpOutBuffer + 12;
      v13 = 0;
      while ( v12[3 * v13 + 1] <= 0x1FEu )
      {
        if ( ++v13 >= v11 )
        {
          v5 = (unsigned int *)AiAlloc(40LL * *((unsigned int *)a2 + 9));
          if ( !v5 )
            break;
          memcpy_0(v5, *((const void **)a2 + 5), 40LL * *((unsigned int *)a2 + 9));
          for ( j = 0; j < *((_DWORD *)a2 + 9); ++j )
            v5[10 * j + 8] = j;
          EtwEventWrite(EventHandle, SrpPolicyHitCountJoinStart, 0, 0);
          qsort(
            v5,
            *((unsigned int *)a2 + 9),
            0x28u,
            (_CoreCrtNonSecureSearchSortCompareFunction)ComparePolicyRulesById);
          qsort(
            lpOutBuffer + 12,
            *((unsigned int *)lpOutBuffer + 5),
            0xCu,
            (_CoreCrtNonSecureSearchSortCompareFunction)CompareRuleHitCountsById);
          v15 = 0;
          for ( k = 0; v15 < *((_DWORD *)lpOutBuffer + 5); ++v15 )
          {
            if ( k >= *((_DWORD *)a2 + 9) )
              break;
            v17 = 3LL * v15;
            memcpy_0(String1, (char *)&v12[v17] + (unsigned int)v12[v17], (unsigned int)v12[v17 + 1]);
            v18 = v12[v17 + 1] & 0xFFFFFFFE;
            if ( v18 >= 0x200 )
              _report_rangecheckfailure();
            *(wchar_t *)((char *)String1 + v18) = 0;
            while ( 1 )
            {
              v19 = _wcsicmp(String1, *(const wchar_t **)&v5[10 * k]);
              if ( v19 <= 0 )
                break;
              if ( ++k >= *((_DWORD *)a2 + 9) )
                goto LABEL_28;
            }
            if ( !v19 )
            {
              v20 = k++;
              *(_DWORD *)(*((_QWORD *)a2 + 5) + 40LL * v5[10 * v20 + 8] + 32) = v12[v17 + 2];
            }
LABEL_28:
            ;
          }
          EtwEventWrite(EventHandle, SrpPolicyHitCountJoinEnd, 0, 0);
          goto LABEL_11;
        }
      }
LABEL_10:
      LastError = 14;
    }
  }
LABEL_11:
  AiFree(v5);
  AiFree(lpOutBuffer);
  return LastError;
}

```

## disassembly

```asm
0x140005be0  mov     [rsp+arg_10], rbx
0x140005be5  push    rbp
0x140005be6  push    rsi
0x140005be7  push    rdi
0x140005be8  push    r12
0x140005bea  push    r13
0x140005bec  push    r14
0x140005bee  push    r15
0x140005bf0  sub     rsp, 260h
0x140005bf7  mov     rax, cs:__security_cookie
0x140005bfe  xor     rax, rsp
0x140005c01  mov     [rsp+298h+var_48], rax
0x140005c09  mov     rsi, rdx
0x140005c0c  xor     r13d, r13d
0x140005c0f  mov     r15, rcx
0x140005c12  mov     [rsp+298h+BytesReturned], r13d
0x140005c17  lea     rdx, aExe; "EXE"
0x140005c1e  mov     edi, r13d
0x140005c21  mov     r14d, r13d
0x140005c24  mov     rcx, [rsi]; String1
0x140005c27  call    cs:__imp__wcsicmp
0x140005c2d  test    eax, eax
0x140005c2f  jz      short loc_140005C4D
0x140005c31  mov     rcx, [rsi]; String1
0x140005c34  lea     rdx, aDll; "DLL"
0x140005c3b  call    cs:__imp__wcsicmp
0x140005c41  test    eax, eax
0x140005c43  jz      short loc_140005C4D
0x140005c45  mov     ebx, r13d
0x140005c48  jmp     loc_140005CCD
0x140005c4d  mov     ebp, 1000h
0x140005c52  xor     ecx, ecx
0x140005c54  jmp     short loc_140005CB3
0x140005c56  mov     r8, [rsi]; unsigned __int16 *
0x140005c59  mov     edx, 10h; unsigned __int64
0x140005c5e  mov     rcx, rbx; unsigned __int16 *
0x140005c61  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140005c66  test    eax, eax
0x140005c68  js      loc_140005EA5
0x140005c6e  mov     [rsp+298h+lpOverlapped], r13; lpOverlapped
0x140005c73  lea     rax, [rsp+298h+BytesReturned]
0x140005c78  mov     [rsp+298h+lpBytesReturned], rax; lpBytesReturned
0x140005c7d  mov     r9d, 24h ; '$'; nInBufferSize
0x140005c83  mov     [rsp+298h+nOutBufferSize], ebp; nOutBufferSize
0x140005c87  mov     r8, rbx; lpInBuffer
0x140005c8a  mov     edx, 229808h; dwIoControlCode
0x140005c8f  mov     [rsp+298h+lpOutBuffer], rbx; lpOutBuffer
0x140005c94  mov     rcx, r15; hDevice
0x140005c97  mov     [rbx+10h], ebp
0x140005c9a  call    cs:__imp_DeviceIoControl
0x140005ca0  test    eax, eax
0x140005ca2  jz      loc_140005E98
0x140005ca8  cmp     [rbx+10h], ebp
0x140005cab  jbe     short loc_140005D0A
0x140005cad  mov     ebp, [rbx+10h]
0x140005cb0  mov     rcx, rbx
0x140005cb3  call    AiFree
0x140005cb8  mov     rcx, rbp
0x140005cbb  call    AiAlloc
0x140005cc0  mov     rbx, rax
0x140005cc3  test    rax, rax
0x140005cc6  jnz     short loc_140005C56
0x140005cc8  mov     edi, 0Eh
0x140005ccd  mov     rcx, r14
0x140005cd0  call    AiFree
0x140005cd5  mov     rcx, rbx
0x140005cd8  call    AiFree
0x140005cdd  mov     eax, edi
0x140005cdf  mov     rcx, [rsp+298h+var_48]
0x140005ce7  xor     rcx, rsp; StackCookie
0x140005cea  call    __security_check_cookie
0x140005cef  mov     rbx, [rsp+298h+arg_10]
0x140005cf7  add     rsp, 260h
0x140005cfe  pop     r15
0x140005d00  pop     r14
0x140005d02  pop     r13
0x140005d04  pop     r12
0x140005d06  pop     rdi
0x140005d07  pop     rsi
0x140005d08  pop     rbp
0x140005d09  retn
0x140005d0a  mov     r8d, [rbx+14h]
0x140005d0e  test    r8d, r8d
0x140005d11  jz      short loc_140005CCD
0x140005d13  lea     r12, [rbx+18h]
0x140005d17  mov     edx, r13d
0x140005d1a  mov     eax, edx
0x140005d1c  lea     rcx, [rax+rax*2]
0x140005d20  cmp     dword ptr [r12+rcx*4+4], 1FEh
0x140005d29  ja      short loc_140005CC8
0x140005d2b  inc     edx
0x140005d2d  cmp     edx, r8d
0x140005d30  jb      short loc_140005D1A
0x140005d32  mov     eax, [rsi+24h]
0x140005d35  lea     rcx, [rax+rax*4]
0x140005d39  shl     rcx, 3
0x140005d3d  call    AiAlloc
0x140005d42  mov     r14, rax
0x140005d45  test    rax, rax
0x140005d48  jz      loc_140005CC8
0x140005d4e  mov     eax, [rsi+24h]
0x140005d51  mov     rcx, r14; void *
0x140005d54  mov     rdx, [rsi+28h]; Src
0x140005d58  lea     r8, [rax+rax*4]
0x140005d5c  shl     r8, 3; Size
0x140005d60  call    memcpy_0
0x140005d65  mov     edx, r13d
0x140005d68  cmp     [rsi+24h], r13d
0x140005d6c  jbe     short loc_140005D80
0x140005d6e  mov     eax, edx
0x140005d70  lea     rcx, [rax+rax*4]
0x140005d74  mov     [r14+rcx*8+20h], edx
0x140005d79  inc     edx
0x140005d7b  cmp     edx, [rsi+24h]
0x140005d7e  jb      short loc_140005D6E
0x140005d80  mov     rcx, cs:?EventHandle@@3_KA; unsigned __int64 EventHandle
0x140005d87  lea     rdx, SrpPolicyHitCountJoinStart
0x140005d8e  xor     r9d, r9d
0x140005d91  xor     r8d, r8d
0x140005d94  call    cs:__imp_EtwEventWrite
0x140005d9a  mov     edx, [rsi+24h]; NumOfElements
0x140005d9d  lea     r9, ?ComparePolicyRulesById@@YAHPEBX0@Z; CompareFunction
0x140005da4  mov     r8d, 28h ; '('; SizeOfElements
0x140005daa  mov     rcx, r14; Base
0x140005dad  call    cs:__imp_qsort
0x140005db3  mov     edx, [rbx+14h]; NumOfElements
0x140005db6  lea     r9, ?CompareRuleHitCountsById@@YAHPEBX0@Z; CompareFunction
0x140005dbd  mov     r8d, 0Ch; SizeOfElements
0x140005dc3  mov     rcx, r12; Base
0x140005dc6  call    cs:__imp_qsort
0x140005dcc  mov     r15d, r13d
0x140005dcf  mov     ebp, r13d
0x140005dd2  cmp     [rbx+14h], r13d
0x140005dd6  jbe     loc_140005E79
0x140005ddc  cmp     ebp, [rsi+24h]
0x140005ddf  jnb     loc_140005E79
0x140005de5  mov     eax, r15d
0x140005de8  lea     rcx, [rax+rax*2]
0x140005dec  lea     r13, ds:0[rcx*4]
0x140005df4  mov     edx, [r12+r13]
0x140005df8  lea     rcx, [rsp+298h+String1]; void *
0x140005dfd  mov     r8d, [r12+r13+4]; Size
0x140005e02  add     rdx, r13
0x140005e05  add     rdx, r12; Src
0x140005e08  call    memcpy_0
0x140005e0d  mov     ecx, [r12+r13+4]
0x140005e12  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140005e16  cmp     rcx, 200h
0x140005e1d  jnb     loc_140005EAF
0x140005e23  xor     eax, eax
0x140005e25  mov     [rsp+rcx+298h+String1], ax
0x140005e2a  mov     eax, ebp
0x140005e2c  lea     rcx, [rsp+298h+String1]; String1
0x140005e31  lea     rdx, [rax+rax*4]
0x140005e35  mov     rdx, [r14+rdx*8]; String2
0x140005e39  call    cs:__imp__wcsicmp
0x140005e3f  test    eax, eax
0x140005e41  jle     short loc_140005E4C
0x140005e43  inc     ebp
0x140005e45  cmp     ebp, [rsi+24h]
0x140005e48  jb      short loc_140005E2A
0x140005e4a  jmp     short loc_140005E6C
0x140005e4c  jnz     short loc_140005E6C
0x140005e4e  mov     eax, ebp
0x140005e50  inc     ebp
0x140005e52  lea     rcx, [rax+rax*4]
0x140005e56  mov     eax, [r14+rcx*8+20h]
0x140005e5b  mov     rcx, [rsi+28h]
0x140005e5f  lea     rdx, [rax+rax*4]
0x140005e63  mov     eax, [r12+r13+8]
0x140005e68  mov     [rcx+rdx*8+20h], eax
0x140005e6c  inc     r15d
0x140005e6f  cmp     r15d, [rbx+14h]
0x140005e73  jb      loc_140005DDC
0x140005e79  mov     rcx, cs:?EventHandle@@3_KA; unsigned __int64 EventHandle
0x140005e80  lea     rdx, SrpPolicyHitCountJoinEnd
0x140005e87  xor     r9d, r9d
0x140005e8a  xor     r8d, r8d
0x140005e8d  call    cs:__imp_EtwEventWrite
0x140005e93  jmp     loc_140005CCD
0x140005e98  call    cs:__imp_GetLastError
0x140005e9e  mov     edi, eax
0x140005ea0  jmp     loc_140005CCD
0x140005ea5  mov     edi, 57h ; 'W'
0x140005eaa  jmp     loc_140005CCD
0x140005eaf  call    __report_rangecheckfailure
```

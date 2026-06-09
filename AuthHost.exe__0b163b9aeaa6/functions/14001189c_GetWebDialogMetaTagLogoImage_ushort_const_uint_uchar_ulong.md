# GetWebDialogMetaTagLogoImage(ushort const *,uint,uchar * *,ulong *)

- ea: `0x14001189c`
- end: `0x140011a9e`
- name: `?GetWebDialogMetaTagLogoImage@@YAJPEBGIPEAPEAEPEAK@Z`
- size: `514`
- prototype: `__int64 __fastcall(LPCWSTR psz, int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000bb4c`

## callees

- `0x140002c98`
- `0x14000429c`
- `0x14001189c`
- `0x140012c38`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400118d3`
- `msvcrt!_wcsicmp` at `0x1400118d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400119b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400119b9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400119f2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400119f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400119fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400119fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011a51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001190b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001190b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001193b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001193b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400119a7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400119a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400118eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400118eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011998`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011998`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x140011989`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x140011989`

## pseudocode

```c
__int64 __fastcall GetWebDialogMetaTagLogoImage(LPCWSTR psz, int a2, unsigned __int8 **a3, unsigned int *a4)
{
  __int64 v4; // rbx
  LPWSTR *v9; // rax
  __int64 v10; // rdi
  int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // r8d
  int v16; // ebx
  HANDLE Thread; // rax
  signed int LastError; // eax

  v4 = qword_14001D978;
  *a3 = 0;
  *a4 = 0;
  while ( 1 )
  {
    if ( !v4 )
    {
      v9 = (LPWSTR *)LocalAlloc(0x40u, 0x30u);
      v10 = (__int64)v9;
      if ( !v9 )
        return 2147942414LL;
      v16 = SHStrDupW(psz, v9 + 2);
      if ( v16 >= 0 )
      {
        InitializeSRWLock((PSRWLOCK)(v10 + 8));
        v16 = -2147483638;
        *(_DWORD *)(v10 + 40) = a2;
        *(_DWORD *)(v10 + 32) = -2147483638;
        *(_DWORD *)(v10 + 36) = GetCurrentThreadId();
        *(_QWORD *)v10 = qword_14001D978;
        qword_14001D978 = v10;
        Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DownloadMetaTagLogoImageThreadProc, (LPVOID)v10, 0, 0);
        if ( Thread )
        {
          CloseHandle(Thread);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              29,
              &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids,
              *(_QWORD *)(v10 + 16));
          }
        }
        else
        {
          LastError = GetLastError();
          v16 = LastError;
          if ( LastError > 0 )
            v16 = (unsigned __int16)LastError | 0x80070000;
          *(_DWORD *)(v10 + 32) = v16;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              28,
              &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids,
              (unsigned int)v16);
          }
        }
      }
      else
      {
        LocalFree((HLOCAL)v10);
      }
      return (unsigned int)v16;
    }
    if ( !_wcsicmp(psz, *(const wchar_t **)(v4 + 16)) )
      break;
    v4 = *(_QWORD *)v4;
  }
  AcquireSRWLockShared((PSRWLOCK)(v4 + 8));
  v12 = *(_DWORD *)(v4 + 32);
  if ( v12 >= 0 )
  {
    v13 = *(_QWORD *)(v4 + 24);
    if ( v13 )
    {
      v14 = *(_QWORD *)(v13 + 8);
      *a3 = *(unsigned __int8 **)(v14 + 8);
      *a4 = *(_DWORD *)v14;
    }
    else
    {
      v12 = -2147418113;
    }
  }
  ReleaseSRWLockShared((PSRWLOCK)(v4 + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_qdS(*((_QWORD *)WPP_GLOBAL_Control + 7), *a4, v15, (unsigned int)*a3, *a4, *(_QWORD *)(v4 + 16));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14001189c  push    rbx
0x14001189e  push    rbp
0x14001189f  push    rsi
0x1400118a0  push    rdi
0x1400118a1  push    r14
0x1400118a3  push    r15
0x1400118a5  sub     rsp, 38h
0x1400118a9  mov     rbx, cs:qword_14001D978
0x1400118b0  mov     rsi, r9
0x1400118b3  mov     r14, r8
0x1400118b6  mov     qword ptr [r8], 0
0x1400118bd  mov     r15d, edx
0x1400118c0  mov     dword ptr [r9], 0
0x1400118c7  mov     rbp, rcx
0x1400118ca  jmp     short loc_1400118E0
0x1400118cc  mov     rdx, [rbx+10h]; String2
0x1400118d0  mov     rcx, rbp; String1
0x1400118d3  call    cs:__imp__wcsicmp
0x1400118d9  test    eax, eax
0x1400118db  jz      short loc_140011907
0x1400118dd  mov     rbx, [rbx]
0x1400118e0  test    rbx, rbx
0x1400118e3  jnz     short loc_1400118CC
0x1400118e5  lea     edx, [rbx+30h]; uBytes
0x1400118e8  lea     ecx, [rbx+40h]; uFlags
0x1400118eb  call    cs:__imp_LocalAlloc
0x1400118f1  mov     rdi, rax
0x1400118f4  test    rax, rax
0x1400118f7  jnz     loc_140011982
0x1400118fd  mov     eax, 8007000Eh
0x140011902  jmp     loc_140011A91
0x140011907  lea     rcx, [rbx+8]; SRWLock
0x14001190b  call    cs:__imp_AcquireSRWLockShared
0x140011911  mov     edi, [rbx+20h]
0x140011914  test    edi, edi
0x140011916  js      short loc_140011937
0x140011918  mov     rcx, [rbx+18h]
0x14001191c  test    rcx, rcx
0x14001191f  jz      short loc_140011932
0x140011921  mov     rcx, [rcx+8]
0x140011925  mov     rax, [rcx+8]
0x140011929  mov     [r14], rax
0x14001192c  mov     eax, [rcx]
0x14001192e  mov     [rsi], eax
0x140011930  jmp     short loc_140011937
0x140011932  mov     edi, 8000FFFFh
0x140011937  lea     rcx, [rbx+8]; SRWLock
0x14001193b  call    cs:__imp_ReleaseSRWLockShared
0x140011941  mov     rcx, cs:WPP_GLOBAL_Control
0x140011948  lea     rax, WPP_GLOBAL_Control
0x14001194f  cmp     rcx, rax
0x140011952  jz      short loc_14001197B
0x140011954  test    byte ptr [rcx+44h], 4
0x140011958  jz      short loc_14001197B
0x14001195a  cmp     byte ptr [rcx+41h], 5
0x14001195e  jb      short loc_14001197B
0x140011960  mov     rdx, [rbx+10h]
0x140011964  mov     r9, [r14]
0x140011967  mov     rcx, [rcx+38h]
0x14001196b  mov     [rsp+68h+lpThreadId], rdx
0x140011970  mov     edx, [rsi]
0x140011972  mov     [rsp+68h+dwCreationFlags], edx
0x140011976  call    WPP_SF_qdS
0x14001197b  mov     eax, edi
0x14001197d  jmp     loc_140011A91
0x140011982  lea     rdx, [rax+10h]; ppwsz
0x140011986  mov     rcx, rbp; psz
0x140011989  call    cs:__imp_SHStrDupW
0x14001198f  mov     ebx, eax
0x140011991  test    eax, eax
0x140011993  jns     short loc_1400119A3
0x140011995  mov     rcx, rdi; hMem
0x140011998  call    cs:__imp_LocalFree
0x14001199e  jmp     loc_140011A8F
0x1400119a3  lea     rcx, [rdi+8]; SRWLock
0x1400119a7  call    cs:__imp_InitializeSRWLock
0x1400119ad  mov     ebx, 8000000Ah
0x1400119b2  mov     [rdi+28h], r15d
0x1400119b6  mov     [rdi+20h], ebx
0x1400119b9  call    cs:__imp_GetCurrentThreadId
0x1400119bf  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x1400119c8  lea     r8, _DownloadMetaTagLogoImageThreadProc; lpStartAddress
0x1400119cf  mov     [rdi+24h], eax
0x1400119d2  mov     r9, rdi; lpParameter
0x1400119d5  mov     rax, cs:qword_14001D978
0x1400119dc  xor     edx, edx; dwStackSize
0x1400119de  xor     ecx, ecx; lpThreadAttributes
0x1400119e0  mov     [rdi], rax
0x1400119e3  mov     cs:qword_14001D978, rdi
0x1400119ea  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1400119f2  call    cs:__imp_CreateThread
0x1400119f8  test    rax, rax
0x1400119fb  jnz     short loc_140011A4E
0x1400119fd  call    cs:__imp_GetLastError
0x140011a03  mov     ebx, eax
0x140011a05  test    eax, eax
0x140011a07  jle     short loc_140011A12
0x140011a09  movzx   ebx, ax
0x140011a0c  or      ebx, 80070000h
0x140011a12  mov     [rdi+20h], ebx
0x140011a15  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a1c  lea     rax, WPP_GLOBAL_Control
0x140011a23  cmp     rcx, rax
0x140011a26  jz      short loc_140011A8F
0x140011a28  test    byte ptr [rcx+44h], 4
0x140011a2c  jz      short loc_140011A8F
0x140011a2e  cmp     byte ptr [rcx+41h], 2
0x140011a32  jb      short loc_140011A8F
0x140011a34  mov     rcx, [rcx+38h]
0x140011a38  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x140011a3f  mov     edx, 1Ch
0x140011a44  mov     r9d, ebx
0x140011a47  call    WPP_SF_d
0x140011a4c  jmp     short loc_140011A8F
0x140011a4e  mov     rcx, rax; hObject
0x140011a51  call    cs:__imp_CloseHandle
0x140011a57  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a5e  lea     rax, WPP_GLOBAL_Control
0x140011a65  cmp     rcx, rax
0x140011a68  jz      short loc_140011A8F
0x140011a6a  test    byte ptr [rcx+44h], 4
0x140011a6e  jz      short loc_140011A8F
0x140011a70  cmp     byte ptr [rcx+41h], 5
0x140011a74  jb      short loc_140011A8F
0x140011a76  mov     r9, [rdi+10h]
0x140011a7a  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x140011a81  mov     rcx, [rcx+38h]
0x140011a85  mov     edx, 1Dh
0x140011a8a  call    WPP_SF_S
0x140011a8f  mov     eax, ebx
0x140011a91  add     rsp, 38h
0x140011a95  pop     r15
0x140011a97  pop     r14
0x140011a99  pop     rdi
0x140011a9a  pop     rsi
0x140011a9b  pop     rbp
0x140011a9c  pop     rbx
0x140011a9d  retn
```

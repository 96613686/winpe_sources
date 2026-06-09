# FveBcdUtil::EnumerateElements(void *,_GUID const *,ulong,_BCD_ELEMENT * *,ulong *)

- ea: `0x18001e4e0`
- end: `0x18001e8ef`
- name: `?EnumerateElements@FveBcdUtil@@CAJPEAXPEBU_GUID@@KPEAPEAU_BCD_ELEMENT@@PEAK@Z`
- size: `1039`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, unsigned int, struct _BCD_ELEMENT **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18006b9f8`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001e4e0`
- `0x18006c0dc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001e55a`
- `ntdll!RtlNtStatusToDosError` at `0x18001e622`
- `ntdll!RtlNtStatusToDosError` at `0x18001e76e`
- `ntdll!RtlNtStatusToDosError` at `0x18001e55a`
- `ntdll!RtlNtStatusToDosError` at `0x18001e622`
- `ntdll!RtlNtStatusToDosError` at `0x18001e76e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e87c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e87c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e6b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e6b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e69b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e868`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e69b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e868`
- `bcd!BcdEnumerateAndUnpackElements` at `0x18001e60d`
- `bcd!BcdEnumerateAndUnpackElements` at `0x18001e760`
- `bcd!BcdEnumerateAndUnpackElements` at `0x18001e60d`
- `bcd!BcdEnumerateAndUnpackElements` at `0x18001e760`
- `bcd!BcdOpenObject` at `0x18001e54c`
- `bcd!BcdOpenObject` at `0x18001e54c`
- `bcd!BcdCloseObject` at `0x18001e8ab`
- `bcd!BcdCloseObject` at `0x18001e8ab`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::EnumerateElements(
        void *a1,
        const struct _GUID *a2,
        __int64 a3,
        struct _BCD_ELEMENT **a4,
        unsigned int *a5)
{
  NTSTATUS v8; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  NTSTATUS v13; // eax
  signed int v14; // eax
  unsigned int v15; // ebx
  HANDLE ProcessHeap; // rax
  struct _BCD_ELEMENT *v17; // rax
  struct _BCD_ELEMENT *v18; // rdi
  NTSTATUS v19; // eax
  signed int v20; // eax
  PVOID *v21; // rcx
  PVOID v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // r8d
  unsigned int *v25; // rax
  PVOID *v26; // rax
  HANDLE v27; // rax
  unsigned int v29; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-24h] BYREF
  __int64 v31; // [rsp+48h] [rbp-20h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp+18h] BYREF

  v30 = 0;
  v29 = 0;
  v31 = 0;
  LODWORD(dwBytes) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids);
  v8 = BcdOpenObject(a1, a2, &v31);
  v9 = RtlNtStatusToDosError(v8);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( (v10 & 0x80000000) != 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
      {
        v12 = 26;
LABEL_13:
        WPP_SF_d(v11[2], v12, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_51;
      }
    }
    goto LABEL_51;
  }
  v13 = BcdEnumerateAndUnpackElements(a1, v31, 28, 0, &dwBytes, &v29);
  if ( v13 == -1073741789 )
  {
    v15 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v17 = (struct _BCD_ELEMENT *)HeapAlloc(ProcessHeap, 8u, v15);
    v18 = v17;
    if ( !v17 )
    {
      v10 = -2147024882;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_51;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          2147942414LL);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 0x40) == 0 )
        goto LABEL_51;
      WPP_SF_d(v11[2], 30, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, 2147942414LL);
LABEL_50:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_51;
    }
    v30 = dwBytes;
    v19 = BcdEnumerateAndUnpackElements(a1, v31, 28, v17, &v30, &v29);
    v20 = RtlNtStatusToDosError(v19);
    v10 = v20;
    if ( v20 > 0 )
      v10 = (unsigned __int16)v20 | 0x80070000;
    if ( (v10 & 0x80000000) == 0 )
    {
      v24 = v29;
      if ( v30 <= (unsigned int)dwBytes && v29 <= (unsigned int)dwBytes >> 4 )
      {
        v25 = a5;
        *a4 = v18;
        *v25 = v24;
        goto LABEL_50;
      }
      v10 = -2147418113;
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_49;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_LLLd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33);
        v26 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v26 == &WPP_GLOBAL_Control || (*((_BYTE *)v26 + 28) & 0x40) == 0 )
      {
LABEL_49:
        v27 = GetProcessHeap();
        HeapFree(v27, 0, v18);
        goto LABEL_50;
      }
      v22 = v26[2];
      v23 = 34;
    }
    else
    {
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_49;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
        v21 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v21 == &WPP_GLOBAL_Control || (*((_BYTE *)v21 + 28) & 0x40) == 0 )
        goto LABEL_49;
      v22 = v21[2];
      v23 = 32;
    }
    WPP_SF_d(v22, v23, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
    goto LABEL_49;
  }
  v14 = RtlNtStatusToDosError(v13);
  v10 = v14;
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0x80070000;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
    {
      v12 = 28;
      goto LABEL_13;
    }
  }
LABEL_51:
  if ( v31 )
  {
    BcdCloseObject(v31);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x20) != 0 )
    WPP_SF_d(v11[2], 35, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18001e4e0  mov     r11, rsp
0x18001e4e3  mov     [r11+18h], r8d
0x18001e4e7  push    rbx
0x18001e4e8  sub     rsp, 60h
0x18001e4ec  xor     eax, eax
0x18001e4ee  mov     [r11+8], rbp
0x18001e4f2  mov     [r11+10h], rsi
0x18001e4f6  mov     rbx, rdx
0x18001e4f9  mov     [r11-18h], r14
0x18001e4fd  mov     rsi, rcx
0x18001e500  mov     r14, r9
0x18001e503  mov     [rsp+68h+var_24], eax
0x18001e507  mov     [rsp+68h+var_28], eax
0x18001e50b  mov     [r11-20h], rax
0x18001e50f  mov     [r11+18h], eax
0x18001e513  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e51a  lea     rbp, WPP_GLOBAL_Control
0x18001e521  cmp     rcx, rbp
0x18001e524  jz      short loc_18001E541
0x18001e526  test    byte ptr [rcx+1Ch], 20h
0x18001e52a  jz      short loc_18001E541
0x18001e52c  mov     rcx, [rcx+10h]
0x18001e530  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e537  mov     edx, 18h
0x18001e53c  call    WPP_SF_
0x18001e541  lea     r8, [rsp+68h+var_20]
0x18001e546  mov     rdx, rbx
0x18001e549  mov     rcx, rsi
0x18001e54c  call    cs:__imp_BcdOpenObject
0x18001e553  nop     dword ptr [rax+rax+00h]
0x18001e558  mov     ecx, eax; Status
0x18001e55a  call    cs:__imp_RtlNtStatusToDosError
0x18001e561  nop     dword ptr [rax+rax+00h]
0x18001e566  mov     ebx, eax
0x18001e568  test    eax, eax
0x18001e56a  jle     short loc_18001E575
0x18001e56c  movzx   ebx, ax
0x18001e56f  or      ebx, 80070000h
0x18001e575  test    ebx, ebx
0x18001e577  jns     short loc_18001E5E5
0x18001e579  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e580  cmp     rcx, rbp
0x18001e583  jz      loc_18001E894
0x18001e589  test    byte ptr [rcx+1Ch], 2
0x18001e58d  jz      short loc_18001E5AE
0x18001e58f  mov     rcx, [rcx+10h]
0x18001e593  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e59a  mov     edx, 19h
0x18001e59f  mov     r9d, ebx
0x18001e5a2  call    WPP_SF_d
0x18001e5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5ae  cmp     rcx, rbp
0x18001e5b1  jz      loc_18001E894
0x18001e5b7  test    byte ptr [rcx+1Ch], 40h
0x18001e5bb  jz      loc_18001E894
0x18001e5c1  mov     edx, 1Ah
0x18001e5c6  mov     rcx, [rcx+10h]
0x18001e5ca  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e5d1  mov     r9d, ebx
0x18001e5d4  call    WPP_SF_d
0x18001e5d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5e0  jmp     loc_18001E894
0x18001e5e5  mov     rdx, [rsp+68h+var_20]
0x18001e5ea  lea     rax, [rsp+68h+var_28]
0x18001e5ef  mov     [rsp+68h+var_40], rax
0x18001e5f4  xor     r9d, r9d
0x18001e5f7  lea     rax, [rsp+68h+dwBytes]
0x18001e5ff  mov     r8d, 1Ch
0x18001e605  mov     rcx, rsi
0x18001e608  mov     [rsp+68h+var_48], rax
0x18001e60d  call    cs:__imp_BcdEnumerateAndUnpackElements
0x18001e614  nop     dword ptr [rax+rax+00h]
0x18001e619  cmp     eax, 0C0000023h
0x18001e61e  jz      short loc_18001E68F
0x18001e620  mov     ecx, eax; Status
0x18001e622  call    cs:__imp_RtlNtStatusToDosError
0x18001e629  nop     dword ptr [rax+rax+00h]
0x18001e62e  mov     ebx, eax
0x18001e630  test    eax, eax
0x18001e632  jle     short loc_18001E63D
0x18001e634  movzx   ebx, ax
0x18001e637  or      ebx, 80070000h
0x18001e63d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e644  cmp     rcx, rbp
0x18001e647  jz      loc_18001E894
0x18001e64d  test    byte ptr [rcx+1Ch], 2
0x18001e651  jz      short loc_18001E672
0x18001e653  mov     rcx, [rcx+10h]
0x18001e657  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e65e  mov     edx, 1Bh
0x18001e663  mov     r9d, ebx
0x18001e666  call    WPP_SF_d
0x18001e66b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e672  cmp     rcx, rbp
0x18001e675  jz      loc_18001E894
0x18001e67b  test    byte ptr [rcx+1Ch], 40h
0x18001e67f  jz      loc_18001E894
0x18001e685  mov     edx, 1Ch
0x18001e68a  jmp     loc_18001E5C6
0x18001e68f  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x18001e696  mov     [rsp+68h+var_10], rdi
0x18001e69b  call    cs:__imp_GetProcessHeap
0x18001e6a2  nop     dword ptr [rax+rax+00h]
0x18001e6a7  mov     r8d, ebx; dwBytes
0x18001e6aa  mov     edx, 8; dwFlags
0x18001e6af  mov     rcx, rax; hHeap
0x18001e6b2  call    cs:__imp_HeapAlloc
0x18001e6b9  nop     dword ptr [rax+rax+00h]
0x18001e6be  mov     rdi, rax
0x18001e6c1  test    rax, rax
0x18001e6c4  jnz     short loc_18001E730
0x18001e6c6  mov     ebx, 8007000Eh
0x18001e6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6d2  cmp     rcx, rbp
0x18001e6d5  jz      loc_18001E88F
0x18001e6db  test    byte ptr [rcx+1Ch], 2
0x18001e6df  jz      short loc_18001E700
0x18001e6e1  mov     rcx, [rcx+10h]
0x18001e6e5  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e6ec  mov     edx, 1Dh
0x18001e6f1  mov     r9d, ebx
0x18001e6f4  call    WPP_SF_d
0x18001e6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e700  cmp     rcx, rbp
0x18001e703  jz      loc_18001E88F
0x18001e709  test    byte ptr [rcx+1Ch], 40h
0x18001e70d  jz      loc_18001E88F
0x18001e713  mov     rcx, [rcx+10h]
0x18001e717  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e71e  mov     edx, 1Eh
0x18001e723  mov     r9d, ebx
0x18001e726  call    WPP_SF_d
0x18001e72b  jmp     loc_18001E888
0x18001e730  mov     eax, dword ptr [rsp+68h+dwBytes]
0x18001e737  mov     r9, rdi
0x18001e73a  mov     rdx, [rsp+68h+var_20]
0x18001e73f  mov     r8d, 1Ch
0x18001e745  mov     [rsp+68h+var_24], eax
0x18001e749  mov     rcx, rsi
0x18001e74c  lea     rax, [rsp+68h+var_28]
0x18001e751  mov     [rsp+68h+var_40], rax
0x18001e756  lea     rax, [rsp+68h+var_24]
0x18001e75b  mov     [rsp+68h+var_48], rax
0x18001e760  call    cs:__imp_BcdEnumerateAndUnpackElements
0x18001e767  nop     dword ptr [rax+rax+00h]
0x18001e76c  mov     ecx, eax; Status
0x18001e76e  call    cs:__imp_RtlNtStatusToDosError
0x18001e775  nop     dword ptr [rax+rax+00h]
0x18001e77a  mov     ebx, eax
0x18001e77c  test    eax, eax
0x18001e77e  jle     short loc_18001E789
0x18001e780  movzx   ebx, ax
0x18001e783  or      ebx, 80070000h
0x18001e789  test    ebx, ebx
0x18001e78b  jns     short loc_18001E7E0
0x18001e78d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e794  cmp     rcx, rbp
0x18001e797  jz      loc_18001E868
0x18001e79d  test    byte ptr [rcx+1Ch], 2
0x18001e7a1  jz      short loc_18001E7C2
0x18001e7a3  mov     rcx, [rcx+10h]
0x18001e7a7  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e7ae  mov     edx, 1Fh
0x18001e7b3  mov     r9d, ebx
0x18001e7b6  call    WPP_SF_d
0x18001e7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7c2  cmp     rcx, rbp
0x18001e7c5  jz      loc_18001E868
0x18001e7cb  test    byte ptr [rcx+1Ch], 40h
0x18001e7cf  jz      loc_18001E868
0x18001e7d5  mov     rcx, [rcx+10h]
0x18001e7d9  mov     edx, 20h ; ' '
0x18001e7de  jmp     short loc_18001E859
0x18001e7e0  mov     r9d, [rsp+68h+var_24]
0x18001e7e5  mov     ecx, dword ptr [rsp+68h+dwBytes]
0x18001e7ec  mov     r8d, [rsp+68h+var_28]
0x18001e7f1  cmp     r9d, ecx
0x18001e7f4  ja      short loc_18001E810
0x18001e7f6  mov     eax, ecx
0x18001e7f8  shr     eax, 4
0x18001e7fb  cmp     r8d, eax
0x18001e7fe  ja      short loc_18001E810
0x18001e800  mov     rax, [rsp+68h+arg_20]
0x18001e808  mov     [r14], rdi
0x18001e80b  mov     [rax], r8d
0x18001e80e  jmp     short loc_18001E888
0x18001e810  mov     ebx, 8000FFFFh
0x18001e815  mov     rax, cs:WPP_GLOBAL_Control
0x18001e81c  cmp     rax, rbp
0x18001e81f  jz      short loc_18001E868
0x18001e821  test    byte ptr [rax+1Ch], 2
0x18001e825  jz      short loc_18001E845
0x18001e827  mov     dword ptr [rsp+68h+var_40], r8d
0x18001e82c  mov     edx, 21h ; '!'
0x18001e831  mov     dword ptr [rsp+68h+var_48], ecx
0x18001e835  mov     rcx, [rax+10h]
0x18001e839  call    WPP_SF_LLLd
0x18001e83e  mov     rax, cs:WPP_GLOBAL_Control
0x18001e845  cmp     rax, rbp
0x18001e848  jz      short loc_18001E868
0x18001e84a  test    byte ptr [rax+1Ch], 40h
0x18001e84e  jz      short loc_18001E868
0x18001e850  mov     rcx, [rax+10h]
0x18001e854  mov     edx, 22h ; '"'
0x18001e859  mov     r9d, ebx
0x18001e85c  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e863  call    WPP_SF_d
0x18001e868  call    cs:__imp_GetProcessHeap
0x18001e86f  nop     dword ptr [rax+rax+00h]
0x18001e874  mov     r8, rdi; lpMem
0x18001e877  xor     edx, edx; dwFlags
0x18001e879  mov     rcx, rax; hHeap
0x18001e87c  call    cs:__imp_HeapFree
0x18001e883  nop     dword ptr [rax+rax+00h]
0x18001e888  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e88f  mov     rdi, [rsp+68h+var_10]
0x18001e894  mov     rax, [rsp+68h+var_20]
0x18001e899  mov     r14, [rsp+68h+var_18]
0x18001e89e  mov     rsi, [rsp+68h+arg_8]
0x18001e8a3  test    rax, rax
0x18001e8a6  jz      short loc_18001E8BE
0x18001e8a8  mov     rcx, rax
0x18001e8ab  call    cs:__imp_BcdCloseObject
0x18001e8b2  nop     dword ptr [rax+rax+00h]
0x18001e8b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8be  cmp     rcx, rbp
0x18001e8c1  mov     rbp, [rsp+68h+arg_0]
0x18001e8c6  jz      short loc_18001E8E6
0x18001e8c8  test    byte ptr [rcx+1Ch], 20h
0x18001e8cc  jz      short loc_18001E8E6
0x18001e8ce  mov     rcx, [rcx+10h]
0x18001e8d2  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001e8d9  mov     edx, 23h ; '#'
0x18001e8de  mov     r9d, ebx
0x18001e8e1  call    WPP_SF_d
0x18001e8e6  mov     eax, ebx
0x18001e8e8  add     rsp, 60h
0x18001e8ec  pop     rbx
0x18001e8ed  retn
```

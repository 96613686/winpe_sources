# MpPluginSendUserModeRegistryData

- ea: `0x18003bdd0`
- end: `0x18003c1b4`
- name: `MpPluginSendUserModeRegistryData`
- size: `996`
- prototype: `__int64 __fastcall(DWORD dwProcessId, __int64, __int64, char, char, __int64, char, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x1800115a0`
- `0x180039bd8`
- `0x18003a39c`
- `0x18003bdd0`
- `0x18003d734`
- `0x18003d758`
- `0x18003d914`
- `0x18007c1a4`
- `0x18008630c`
- `0x18008e744`
- `0x18008e848`
- `0x1800925c8`
- `0x1800d4220`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003c09b`
- `KERNEL32!GetCurrentThreadId` at `0x18003c09b`
- `KERNEL32!ProcessIdToSessionId` at `0x18003c079`
- `KERNEL32!ProcessIdToSessionId` at `0x18003c079`
- `KERNEL32!CloseHandle` at `0x18003c069`
- `KERNEL32!CloseHandle` at `0x18003c069`
- `KERNEL32!GetProcessTimes` at `0x18003c060`
- `KERNEL32!GetProcessTimes` at `0x18003c060`
- `KERNEL32!GetLastError` at `0x18003bfe7`
- `KERNEL32!GetLastError` at `0x18003bfe7`
- `KERNEL32!OpenProcess` at `0x18003bfd9`
- `KERNEL32!OpenProcess` at `0x18003bfd9`

## pseudocode

```c
__int64 __fastcall MpPluginSendUserModeRegistryData(
        DWORD dwProcessId,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8)
{
  __int64 v13; // r8
  __int64 v14; // r8
  int v15; // edi
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // eax
  HANDLE v20; // rdi
  signed int LastError; // eax
  signed int v22; // ebx
  __int64 v23; // rbx
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+68h] [rbp-98h]
  __int128 v27; // [rsp+78h] [rbp-88h]
  _OWORD v28[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+A8h] [rbp-58h] BYREF
  int v30; // [rsp+B0h] [rbp-50h]
  DWORD v31; // [rsp+B4h] [rbp-4Ch]
  DWORD v32; // [rsp+B8h] [rbp-48h]
  DWORD CurrentThreadId; // [rsp+BCh] [rbp-44h]
  int v34; // [rsp+C0h] [rbp-40h]
  int v35; // [rsp+C4h] [rbp-3Ch]
  signed __int64 v36; // [rsp+C8h] [rbp-38h]
  struct _FILETIME v37; // [rsp+D0h] [rbp-30h]
  _QWORD *v38; // [rsp+D8h] [rbp-28h]
  _QWORD v39[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v40; // [rsp+F0h] [rbp-10h]
  int v41; // [rsp+F4h] [rbp-Ch]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  int v43; // [rsp+100h] [rbp+0h]
  int v44; // [rsp+104h] [rbp+4h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  int v46; // [rsp+110h] [rbp+10h]
  int v47; // [rsp+114h] [rbp+14h]
  __int64 v48; // [rsp+118h] [rbp+18h]
  DWORD pSessionId; // [rsp+120h] [rbp+20h] BYREF
  struct _FILETIME CreationTime; // [rsp+128h] [rbp+28h] BYREF
  struct _FILETIME UserTime; // [rsp+130h] [rbp+30h] BYREF
  struct _FILETIME KernelTime; // [rsp+138h] [rbp+38h] BYREF
  struct _FILETIME ExitTime; // [rsp+140h] [rbp+40h] BYREF
  __int128 v54; // [rsp+148h] [rbp+48h] BYREF
  __int64 v55; // [rsp+158h] [rbp+58h]

  v24 = a8;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  sub_18007C1A4(lpMem, &v25);
  if ( (_DWORD)v27 != 1 )
    return 0;
  if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 0x10) != 0 )
    sub_18003D914(*((_QWORD *)off_180119DF0 + 2), a2, a3, a4, a5, a7);
  v55 = 0;
  v54 = 0;
  v13 = -1;
  v25 = 0;
  v26 = 0;
  do
    ++v13;
  while ( *(_WORD *)(a3 + 2 * v13) );
  sub_180039BD8(&v25, a3);
  v14 = -1;
  memset(v28, 0, sizeof(v28));
  do
    ++v14;
  while ( *(_WORD *)(a2 + 2 * v14) );
  sub_180039BD8(v28, a2);
  v15 = sub_18008E848(&v54, v28, &v25);
  sub_18003A39C(v28);
  sub_18003A39C(&v25);
  if ( v15 >= 0 )
  {
    v48 = 0;
    v39[0] = &v54;
    v39[1] = a6;
    v40 = a5;
    if ( a4 )
    {
      v16 = a4 - 1;
      if ( !v16 )
      {
        v19 = 4;
        goto LABEL_24;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        v19 = 1;
        goto LABEL_24;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        v19 = 7;
        goto LABEL_24;
      }
      if ( v18 == 1 )
      {
        v19 = 3;
LABEL_24:
        v43 = a7;
        v42 = v24;
        v41 = v19;
        v44 = v19;
        v45 = 0;
        v46 = 2;
        v47 = 1;
        v20 = OpenProcess(0x400u, 0, dwProcessId);
        if ( v20 )
          goto LABEL_32;
        LastError = GetLastError();
        v22 = LastError;
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        if ( v22 >= 0 )
        {
LABEL_32:
          CreationTime = 0;
          ExitTime = 0;
          KernelTime = 0;
          UserTime = 0;
          GetProcessTimes(v20, &CreationTime, &ExitTime, &KernelTime, &UserTime);
          CloseHandle(v20);
          pSessionId = 0;
          ProcessIdToSessionId(dwProcessId, &pSessionId);
          v37 = CreationTime;
          v32 = pSessionId;
          v29 = 0;
          v35 = 0;
          v30 = 0;
          v31 = dwProcessId;
          CurrentThreadId = GetCurrentThreadId();
          v34 = 32;
          v36 = _InterlockedIncrement64(&qword_18011FE40);
          v24 = 0;
          v38 = v39;
          sub_18008630C((char *)lpMem + 120, &v24);
          v23 = v24;
          if ( v24 )
          {
            v15 = sub_1800925C8(v24, &v29);
            if ( v15 < 0 && off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
              sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 50, &MessageGuid, (unsigned int)v15);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v23 + 8), 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (**(void (__fastcall ***)(__int64, __int64))v23)(v23, 1);
            }
          }
          else
          {
            if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 4) != 0 )
              sub_18003D734(*((_QWORD *)off_180119DF0 + 2), (unsigned int)(v24 + 49), &MessageGuid);
            v15 = -2147467259;
          }
        }
        else
        {
          if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
            sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 48, &MessageGuid, (unsigned int)v22);
          v15 = v22;
        }
        goto LABEL_43;
      }
    }
    v19 = 0;
    goto LABEL_24;
  }
  if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
    sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 47, &MessageGuid, (unsigned int)v15);
LABEL_43:
  sub_18008E744(&v54);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003bdd0  mov     [rsp-8+arg_18], rbx
0x18003bdd5  push    rbp
0x18003bdd6  push    rsi
0x18003bdd7  push    rdi
0x18003bdd8  push    r12
0x18003bdda  push    r13
0x18003bddc  push    r14
0x18003bdde  push    r15
0x18003bde0  lea     rbp, [rsp-70h]
0x18003bde5  sub     rsp, 170h
0x18003bdec  mov     rax, cs:__security_cookie
0x18003bdf3  xor     rax, rsp
0x18003bdf6  mov     [rbp+0A0h+var_40], rax
0x18003bdfa  mov     rax, [rbp+0A0h+arg_38]
0x18003be01  xorps   xmm0, xmm0
0x18003be04  mov     r13, [rbp+0A0h+arg_28]
0x18003be0b  mov     rsi, rdx
0x18003be0e  mov     r12d, ecx
0x18003be11  mov     [rsp+1A0h+var_150], rax
0x18003be16  mov     rcx, cs:lpMem
0x18003be1d  lea     rdx, [rsp+1A0h+var_148]
0x18003be22  movups  [rsp+1A0h+var_148], xmm0
0x18003be27  mov     ebx, r9d
0x18003be2a  mov     rdi, r8
0x18003be2d  movups  [rsp+1A0h+var_138], xmm0
0x18003be32  movups  [rsp+1A0h+var_128], xmm0
0x18003be37  call    sub_18007C1A4
0x18003be3c  cmp     dword ptr [rsp+1A0h+var_128], 1
0x18003be41  jz      short loc_18003BE4A
0x18003be43  xor     eax, eax
0x18003be45  jmp     loc_18003C18D
0x18003be4a  mov     rcx, cs:off_180119DF0
0x18003be51  lea     rax, off_180119DF0
0x18003be58  mov     r15d, dword ptr [rbp+0A0h+arg_30]
0x18003be5f  mov     r14d, dword ptr [rbp+0A0h+arg_20]
0x18003be66  cmp     rcx, rax
0x18003be69  jz      short loc_18003BE95
0x18003be6b  test    byte ptr [rcx+1Ch], 10h
0x18003be6f  jz      short loc_18003BE95
0x18003be71  mov     rcx, [rcx+10h]; LoggerHandle
0x18003be75  mov     r9d, r12d
0x18003be78  mov     dword ptr [rsp+1A0h+var_160], r15d; char
0x18003be7d  mov     dword ptr [rsp+1A0h+var_168], r14d; char
0x18003be82  mov     dword ptr [rsp+1A0h+var_170], ebx; char
0x18003be86  mov     [rsp+1A0h+var_178], rdi; __int64
0x18003be8b  mov     [rsp+1A0h+lpUserTime], rsi; __int64
0x18003be90  call    sub_18003D914
0x18003be95  xorps   xmm0, xmm0
0x18003be98  xor     eax, eax
0x18003be9a  xorps   xmm1, xmm1
0x18003be9d  mov     [rbp+0A0h+var_48], rax
0x18003bea1  movups  [rbp+0A0h+var_58], xmm0
0x18003bea5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003bea9  movups  [rsp+1A0h+var_148], xmm0
0x18003beae  movdqu  [rsp+1A0h+var_138], xmm1
0x18003beb4  inc     r8
0x18003beb7  cmp     [rdi+r8*2], ax
0x18003bebc  jnz     short loc_18003BEB4
0x18003bebe  mov     rdx, rdi
0x18003bec1  lea     rcx, [rsp+1A0h+var_148]
0x18003bec6  call    sub_180039BD8
0x18003becb  xorps   xmm0, xmm0
0x18003bece  xorps   xmm1, xmm1
0x18003bed1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003bed5  movups  [rbp+0A0h+var_118], xmm0
0x18003bed9  xor     eax, eax
0x18003bedb  movdqu  [rbp+0A0h+var_108], xmm1
0x18003bee0  inc     r8
0x18003bee3  cmp     [rsi+r8*2], ax
0x18003bee8  jnz     short loc_18003BEE0
0x18003beea  mov     rdx, rsi
0x18003beed  lea     rcx, [rbp+0A0h+var_118]
0x18003bef1  call    sub_180039BD8
0x18003bef6  lea     r8, [rsp+1A0h+var_148]
0x18003befb  lea     rdx, [rbp+0A0h+var_118]
0x18003beff  lea     rcx, [rbp+0A0h+var_58]
0x18003bf03  call    sub_18008E848
0x18003bf08  lea     rcx, [rbp+0A0h+var_118]
0x18003bf0c  mov     edi, eax
0x18003bf0e  call    sub_18003A39C
0x18003bf13  lea     rcx, [rsp+1A0h+var_148]
0x18003bf18  call    sub_18003A39C
0x18003bf1d  xor     esi, esi
0x18003bf1f  test    edi, edi
0x18003bf21  jns     short loc_18003BF5F
0x18003bf23  mov     rcx, cs:off_180119DF0
0x18003bf2a  lea     rax, off_180119DF0
0x18003bf31  cmp     rcx, rax
0x18003bf34  jz      loc_18003C182
0x18003bf3a  test    byte ptr [rcx+1Ch], 1
0x18003bf3e  jz      loc_18003C182
0x18003bf44  mov     rcx, [rcx+10h]
0x18003bf48  lea     edx, [rsi+2Fh]
0x18003bf4b  mov     r9d, edi
0x18003bf4e  lea     r8, MessageGuid
0x18003bf55  call    sub_18003D758
0x18003bf5a  jmp     loc_18003C182
0x18003bf5f  mov     [rbp+0A0h+var_88], rsi
0x18003bf63  lea     rax, [rbp+0A0h+var_58]
0x18003bf67  mov     [rbp+0A0h+var_C0], rax
0x18003bf6b  mov     [rbp+0A0h+var_B8], r13
0x18003bf6f  mov     [rbp+0A0h+var_B0], r14d
0x18003bf73  test    ebx, ebx
0x18003bf75  jz      short loc_18003BFA5
0x18003bf77  sub     ebx, 1
0x18003bf7a  jz      short loc_18003BF9E
0x18003bf7c  sub     ebx, 1
0x18003bf7f  jz      short loc_18003BF97
0x18003bf81  sub     ebx, 1
0x18003bf84  jz      short loc_18003BF90
0x18003bf86  cmp     ebx, 1
0x18003bf89  jnz     short loc_18003BFA5
0x18003bf8b  lea     eax, [rbx+2]
0x18003bf8e  jmp     short loc_18003BFA7
0x18003bf90  mov     eax, 7
0x18003bf95  jmp     short loc_18003BFA7
0x18003bf97  mov     eax, 1
0x18003bf9c  jmp     short loc_18003BFA7
0x18003bf9e  mov     eax, 4
0x18003bfa3  jmp     short loc_18003BFA7
0x18003bfa5  mov     eax, esi
0x18003bfa7  mov     rcx, [rsp+1A0h+var_150]
0x18003bfac  mov     r8d, r12d; dwProcessId
0x18003bfaf  mov     [rbp+0A0h+var_A0], r15d
0x18003bfb3  xor     edx, edx; bInheritHandle
0x18003bfb5  mov     [rbp+0A0h+var_A8], rcx
0x18003bfb9  mov     r15d, 1
0x18003bfbf  mov     ecx, 400h; dwDesiredAccess
0x18003bfc4  mov     [rbp+0A0h+var_AC], eax
0x18003bfc7  mov     [rbp+0A0h+var_9C], eax
0x18003bfca  mov     [rbp+0A0h+var_98], rsi
0x18003bfce  mov     [rbp+0A0h+var_90], 2
0x18003bfd5  mov     [rbp+0A0h+var_8C], r15d
0x18003bfd9  call    cs:OpenProcess
0x18003bfdf  mov     rdi, rax
0x18003bfe2  test    rax, rax
0x18003bfe5  jnz     short loc_18003C038
0x18003bfe7  call    cs:GetLastError
0x18003bfed  mov     ebx, eax
0x18003bfef  test    eax, eax
0x18003bff1  jle     short loc_18003BFFC
0x18003bff3  movzx   ebx, ax
0x18003bff6  or      ebx, 80070000h
0x18003bffc  test    ebx, ebx
0x18003bffe  jns     short loc_18003C038
0x18003c000  mov     rcx, cs:off_180119DF0
0x18003c007  lea     rax, off_180119DF0
0x18003c00e  cmp     rcx, rax
0x18003c011  jz      short loc_18003C031
0x18003c013  test    [rcx+1Ch], r15b
0x18003c017  jz      short loc_18003C031
0x18003c019  mov     rcx, [rcx+10h]
0x18003c01d  lea     r8, MessageGuid
0x18003c024  mov     edx, 30h ; '0'
0x18003c029  mov     r9d, ebx
0x18003c02c  call    sub_18003D758
0x18003c031  mov     edi, ebx
0x18003c033  jmp     loc_18003C182
0x18003c038  lea     rax, [rbp+0A0h+UserTime]
0x18003c03c  mov     qword ptr [rbp+0A0h+CreationTime.dwLowDateTime], rsi
0x18003c040  lea     r9, [rbp+0A0h+KernelTime]; lpKernelTime
0x18003c044  mov     [rsp+1A0h+lpUserTime], rax; lpUserTime
0x18003c049  lea     r8, [rbp+0A0h+ExitTime]; lpExitTime
0x18003c04d  mov     qword ptr [rbp+0A0h+ExitTime.dwLowDateTime], rsi
0x18003c051  lea     rdx, [rbp+0A0h+CreationTime]; lpCreationTime
0x18003c055  mov     qword ptr [rbp+0A0h+KernelTime.dwLowDateTime], rsi
0x18003c059  mov     rcx, rdi; hProcess
0x18003c05c  mov     qword ptr [rbp+0A0h+UserTime.dwLowDateTime], rsi
0x18003c060  call    cs:GetProcessTimes
0x18003c066  mov     rcx, rdi; hObject
0x18003c069  call    cs:CloseHandle
0x18003c06f  lea     rdx, [rbp+0A0h+pSessionId]; pSessionId
0x18003c073  mov     [rbp+0A0h+pSessionId], esi
0x18003c076  mov     ecx, r12d; dwProcessId
0x18003c079  call    cs:ProcessIdToSessionId
0x18003c07f  mov     rax, qword ptr [rbp+0A0h+CreationTime.dwLowDateTime]
0x18003c083  mov     [rbp+0A0h+var_D0], rax
0x18003c087  mov     eax, [rbp+0A0h+pSessionId]
0x18003c08a  mov     [rbp+0A0h+var_E8], eax
0x18003c08d  mov     [rbp+0A0h+var_F8], rsi
0x18003c091  mov     [rbp+0A0h+var_DC], esi
0x18003c094  mov     [rbp+0A0h+var_F0], esi
0x18003c097  mov     [rbp+0A0h+var_EC], r12d
0x18003c09b  call    cs:GetCurrentThreadId
0x18003c0a1  mov     [rbp+0A0h+var_E4], eax
0x18003c0a4  mov     rax, r15
0x18003c0a7  lock xadd cs:qword_18011FE40, rax
0x18003c0b0  mov     rcx, cs:lpMem
0x18003c0b7  lea     rdx, [rsp+1A0h+var_150]
0x18003c0bc  add     rax, r15
0x18003c0bf  mov     [rbp+0A0h+var_E0], 20h ; ' '
0x18003c0c6  mov     [rbp+0A0h+var_D8], rax
0x18003c0ca  add     rcx, 78h ; 'x'
0x18003c0ce  lea     rax, [rbp+0A0h+var_C0]
0x18003c0d2  mov     [rsp+1A0h+var_150], rsi
0x18003c0d7  mov     [rbp+0A0h+var_C8], rax
0x18003c0db  call    sub_18008630C
0x18003c0e0  mov     rbx, [rsp+1A0h+var_150]
0x18003c0e5  test    rbx, rbx
0x18003c0e8  jnz     short loc_18003C11D
0x18003c0ea  mov     rcx, cs:off_180119DF0
0x18003c0f1  lea     rax, off_180119DF0
0x18003c0f8  cmp     rcx, rax
0x18003c0fb  jz      short loc_18003C116
0x18003c0fd  test    byte ptr [rcx+1Ch], 4
0x18003c101  jz      short loc_18003C116
0x18003c103  mov     rcx, [rcx+10h]
0x18003c107  lea     edx, [rbx+31h]
0x18003c10a  lea     r8, MessageGuid
0x18003c111  call    sub_18003D734
0x18003c116  mov     edi, 80004005h
0x18003c11b  jmp     short loc_18003C182
0x18003c11d  lea     rdx, [rbp+0A0h+var_F8]
0x18003c121  mov     rcx, rbx
0x18003c124  call    sub_1800925C8
0x18003c129  mov     edi, eax
0x18003c12b  test    eax, eax
0x18003c12d  jns     short loc_18003C160
0x18003c12f  mov     rcx, cs:off_180119DF0
0x18003c136  lea     rax, off_180119DF0
0x18003c13d  cmp     rcx, rax
0x18003c140  jz      short loc_18003C160
0x18003c142  test    [rcx+1Ch], r15b
0x18003c146  jz      short loc_18003C160
0x18003c148  mov     rcx, [rcx+10h]
0x18003c14c  lea     r8, MessageGuid
0x18003c153  mov     edx, 32h ; '2'
0x18003c158  mov     r9d, edi
0x18003c15b  call    sub_18003D758
0x18003c160  or      eax, 0FFFFFFFFh
0x18003c163  lock xadd [rbx+8], eax
0x18003c168  sub     eax, r15d
0x18003c16b  jg      short loc_18003C182
0x18003c16d  lfence
0x18003c170  mov     rax, [rbx]
0x18003c173  mov     edx, r15d
0x18003c176  mov     rcx, rbx
0x18003c179  mov     rax, [rax]
0x18003c17c  call    cs:__guard_dispatch_icall_fptr
0x18003c182  lea     rcx, [rbp+0A0h+var_58]
0x18003c186  call    sub_18008E744
0x18003c18b  mov     eax, edi
0x18003c18d  mov     rcx, [rbp+0A0h+var_40]
0x18003c191  xor     rcx, rsp; StackCookie
0x18003c194  call    __security_check_cookie
0x18003c199  mov     rbx, [rsp+1A0h+arg_18]
0x18003c1a1  add     rsp, 170h
0x18003c1a8  pop     r15
0x18003c1aa  pop     r14
0x18003c1ac  pop     r13
0x18003c1ae  pop     r12
0x18003c1b0  pop     rdi
0x18003c1b1  pop     rsi
0x18003c1b2  pop     rbp
0x18003c1b3  retn
```

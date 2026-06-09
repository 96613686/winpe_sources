# GetAppInfo(ulong,_APF_APP_INFO * *)

- ea: `0x180006740`
- end: `0x180006abd`
- name: `?GetAppInfo@@YAJKPEAPEAU_APF_APP_INFO@@@Z`
- size: `893`
- prototype: `__int64 __fastcall(DWORD dwProcessId, struct _APF_APP_INFO **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800063c8`
- `0x180007660`

## callees

- `0x180001930`
- `0x180001fcc`
- `0x1800061ac`
- `0x180006740`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006997`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800067da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800067da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a9e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006772`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006772`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180006850`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1800068d8`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180006850`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1800068d8`

## pseudocode

```c
__int64 __fastcall GetAppInfo(DWORD dwProcessId, struct _APF_APP_INFO **a2)
{
  HANDLE v3; // rax
  void *v4; // rbp
  signed int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  signed int LastError; // eax
  _DWORD *v11; // rdi
  int SecurityAttributesToken; // ebx
  __int64 v13; // rax
  __int64 v14; // rbx
  unsigned __int16 v15; // ax
  unsigned int v16; // esi
  struct _APF_APP_INFO *v17; // r14
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  v3 = OpenProcess(0x400u, 0, dwProcessId);
  v4 = v3;
  if ( v3 )
  {
    if ( OpenProcessToken(v3, 8u, &TokenHandle) )
    {
      if ( (unsigned int)NtQuerySecurityAttributesToken(TokenHandle, &qword_18000A148, 1) == -1073741789 )
      {
        v11 = operator new[](0, (const struct std::nothrow_t *)&std::nothrow);
        if ( v11 )
        {
          SecurityAttributesToken = NtQuerySecurityAttributesToken(TokenHandle, &qword_18000A148, 1);
          if ( SecurityAttributesToken >= 0 )
          {
            if ( v11[1] == 1 && (v13 = *((_QWORD *)v11 + 1), *(_WORD *)(v13 + 16) == 3) && *(_DWORD *)(v13 + 24) >= 3u )
            {
              v14 = *(_QWORD *)(v13 + 32);
              if ( *(_QWORD *)(v14 + 40)
                && (v15 = *(_WORD *)(v14 + 32)) != 0
                && (v15 & 1) == 0
                && *(_WORD *)(v14 + 34) >= v15 )
              {
                v16 = 0;
                while ( 1 )
                {
                  v17 = (struct _APF_APP_INFO *)(&g_SupportedAppList + 6 * v16);
                  if ( *(_WORD *)(v14 + 32) == *(_WORD *)v17
                    && !(unsigned int)_o__wcsnicmp(
                                        *(_QWORD *)(v14 + 40),
                                        *(&g_SupportedAppList + 6 * v16 + 1),
                                        (unsigned __int64)*(unsigned __int16 *)(v14 + 32) >> 1) )
                  {
                    break;
                  }
                  if ( ++v16 >= 3 )
                  {
                    v6 = -2147023728;
                    goto LABEL_50;
                  }
                }
                *a2 = v17;
                v6 = 0;
              }
              else
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 28) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    17,
                    &WPP_90890ce224d03ac7b34da71504f71581_Traceguids,
                    3221225604LL);
                }
                v6 = -805306236;
              }
            }
            else
            {
              v6 = -2147023728;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((char *)WPP_GLOBAL_Control + 28) < 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  16,
                  &WPP_90890ce224d03ac7b34da71504f71581_Traceguids,
                  2147943568LL);
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 28) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                &WPP_90890ce224d03ac7b34da71504f71581_Traceguids,
                (unsigned int)SecurityAttributesToken);
            }
            v6 = SecurityAttributesToken | 0x10000000;
          }
LABEL_50:
          operator delete(v11);
        }
        else
        {
          v6 = -2147024888;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 13;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v9 = 2147943568LL;
        v6 = -2147023728;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 14;
          goto LABEL_55;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 12;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 11;
LABEL_8:
      v9 = v6;
LABEL_55:
      WPP_SF_d(v7[2], v8, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids, v9);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 )
    CloseHandle(v4);
  return v6;
}

```

## disassembly

```asm
0x180006740  mov     rax, rsp
0x180006743  mov     [rax+8], rbx
0x180006747  mov     [rax+20h], rbp
0x18000674b  push    rsi
0x18000674c  push    rdi
0x18000674d  push    r12
0x18000674f  push    r14
0x180006751  push    r15
0x180006753  sub     rsp, 30h
0x180006757  xor     r12d, r12d
0x18000675a  mov     r15, rdx
0x18000675d  mov     [rdx], r12
0x180006760  mov     r8d, ecx; dwProcessId
0x180006763  xor     edx, edx; bInheritHandle
0x180006765  mov     [rax+18h], r12
0x180006769  mov     ecx, 400h; dwDesiredAccess
0x18000676e  mov     [rax+10h], r12d
0x180006772  call    cs:__imp_OpenProcess
0x180006778  mov     rbp, rax
0x18000677b  test    rax, rax
0x18000677e  jnz     short loc_1800067CD
0x180006780  call    cs:__imp_GetLastError
0x180006786  mov     ebx, eax
0x180006788  test    eax, eax
0x18000678a  jle     short loc_180006795
0x18000678c  movzx   ebx, ax
0x18000678f  or      ebx, 80070000h
0x180006795  mov     rcx, cs:WPP_GLOBAL_Control
0x18000679c  lea     rax, WPP_GLOBAL_Control
0x1800067a3  cmp     rcx, rax
0x1800067a6  jz      loc_180006A86
0x1800067ac  test    byte ptr [rcx+1Ch], 80h
0x1800067b0  jz      loc_180006A86
0x1800067b6  cmp     byte ptr [rcx+19h], 2
0x1800067ba  jb      loc_180006A86
0x1800067c0  mov     edx, 0Bh
0x1800067c5  mov     r9d, ebx
0x1800067c8  jmp     loc_180006A76
0x1800067cd  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800067d2  mov     edx, 8; DesiredAccess
0x1800067d7  mov     rcx, rbp; ProcessHandle
0x1800067da  call    cs:__imp_OpenProcessToken
0x1800067e0  test    eax, eax
0x1800067e2  jnz     short loc_18000682B
0x1800067e4  call    cs:__imp_GetLastError
0x1800067ea  mov     ebx, eax
0x1800067ec  test    eax, eax
0x1800067ee  jle     short loc_1800067F9
0x1800067f0  movzx   ebx, ax
0x1800067f3  or      ebx, 80070000h
0x1800067f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006800  lea     rax, WPP_GLOBAL_Control
0x180006807  cmp     rcx, rax
0x18000680a  jz      loc_180006A86
0x180006810  test    byte ptr [rcx+1Ch], 80h
0x180006814  jz      loc_180006A86
0x18000681a  cmp     byte ptr [rcx+19h], 2
0x18000681e  jb      loc_180006A86
0x180006824  mov     edx, 0Ch
0x180006829  jmp     short loc_1800067C5
0x18000682b  mov     rcx, [rsp+58h+TokenHandle]
0x180006830  lea     rax, [rsp+58h+arg_8]
0x180006835  mov     [rsp+58h+var_30], rax
0x18000683a  lea     rdx, qword_18000A148
0x180006841  mov     eax, dword ptr [rsp+58h+arg_8]
0x180006845  xor     r9d, r9d
0x180006848  mov     [rsp+58h+var_38], eax
0x18000684c  lea     r8d, [r9+1]
0x180006850  call    cs:__imp_NtQuerySecurityAttributesToken
0x180006856  cmp     eax, 0C0000023h
0x18000685b  jnz     loc_180006A49
0x180006861  mov     ecx, dword ptr [rsp+58h+arg_8]; unsigned __int64
0x180006865  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000686c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006871  mov     rdi, rax
0x180006874  test    rax, rax
0x180006877  jnz     short loc_1800068B1
0x180006879  mov     ebx, 80070008h
0x18000687e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006885  lea     rax, WPP_GLOBAL_Control
0x18000688c  cmp     rcx, rax
0x18000688f  jz      loc_180006A86
0x180006895  test    byte ptr [rcx+1Ch], 80h
0x180006899  jz      loc_180006A86
0x18000689f  cmp     byte ptr [rcx+19h], 2
0x1800068a3  jb      loc_180006A86
0x1800068a9  lea     edx, [rdi+0Dh]
0x1800068ac  jmp     loc_1800067C5
0x1800068b1  mov     rcx, [rsp+58h+TokenHandle]
0x1800068b6  lea     rax, [rsp+58h+arg_8]
0x1800068bb  mov     [rsp+58h+var_30], rax
0x1800068c0  lea     rdx, qword_18000A148
0x1800068c7  mov     eax, dword ptr [rsp+58h+arg_8]
0x1800068cb  mov     r9, rdi
0x1800068ce  mov     r8d, 1
0x1800068d4  mov     [rsp+58h+var_38], eax
0x1800068d8  call    cs:__imp_NtQuerySecurityAttributesToken
0x1800068de  mov     ebx, eax
0x1800068e0  test    eax, eax
0x1800068e2  jns     short loc_180006924
0x1800068e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068eb  lea     rax, WPP_GLOBAL_Control
0x1800068f2  cmp     rcx, rax
0x1800068f5  jz      short loc_18000691B
0x1800068f7  test    byte ptr [rcx+1Ch], 80h
0x1800068fb  jz      short loc_18000691B
0x1800068fd  cmp     byte ptr [rcx+19h], 2
0x180006901  jb      short loc_18000691B
0x180006903  mov     rcx, [rcx+10h]
0x180006907  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x18000690e  mov     edx, 0Fh
0x180006913  mov     r9d, ebx
0x180006916  call    WPP_SF_d
0x18000691b  bts     ebx, 1Ch
0x18000691f  jmp     loc_180006A3F
0x180006924  cmp     dword ptr [rdi+4], 1
0x180006928  jnz     loc_180006A02
0x18000692e  mov     rax, [rdi+8]
0x180006932  mov     ecx, 3
0x180006937  cmp     [rax+10h], cx
0x18000693b  jnz     loc_180006A02
0x180006941  cmp     [rax+18h], ecx
0x180006944  jb      loc_180006A02
0x18000694a  mov     rbx, [rax+20h]
0x18000694e  cmp     [rbx+28h], r12
0x180006952  jz      short loc_1800069C1
0x180006954  movzx   eax, word ptr [rbx+20h]
0x180006958  test    ax, ax
0x18000695b  jz      short loc_1800069C1
0x18000695d  test    al, 1
0x18000695f  jnz     short loc_1800069C1
0x180006961  cmp     [rbx+22h], ax
0x180006965  jb      short loc_1800069C1
0x180006967  mov     esi, r12d
0x18000696a  lea     r9, ?g_SupportedAppList@@3PAU_APF_APP_INFO@@A; "TV"
0x180006971  movzx   ecx, word ptr [rbx+20h]
0x180006975  mov     eax, esi
0x180006977  lea     rdx, [rax+rax*2]
0x18000697b  add     rdx, rdx
0x18000697e  lea     r14, [r9+rdx*8]
0x180006982  cmp     cx, [r14]
0x180006986  jnz     short loc_1800069A8
0x180006988  mov     rdx, [r9+rdx*8+8]
0x18000698d  mov     r8d, ecx
0x180006990  mov     rcx, [rbx+28h]
0x180006994  shr     r8, 1
0x180006997  call    cs:__imp__o__wcsnicmp
0x18000699d  test    eax, eax
0x18000699f  jz      short loc_1800069B9
0x1800069a1  lea     r9, ?g_SupportedAppList@@3PAU_APF_APP_INFO@@A; "TV"
0x1800069a8  inc     esi
0x1800069aa  cmp     esi, 3
0x1800069ad  jb      short loc_180006971
0x1800069af  mov     ebx, 80070490h
0x1800069b4  jmp     loc_180006A3F
0x1800069b9  mov     [r15], r14
0x1800069bc  mov     ebx, r12d
0x1800069bf  jmp     short loc_180006A3F
0x1800069c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069c8  lea     rax, WPP_GLOBAL_Control
0x1800069cf  cmp     rcx, rax
0x1800069d2  jz      short loc_1800069FB
0x1800069d4  test    byte ptr [rcx+1Ch], 80h
0x1800069d8  jz      short loc_1800069FB
0x1800069da  cmp     byte ptr [rcx+19h], 2
0x1800069de  jb      short loc_1800069FB
0x1800069e0  mov     rcx, [rcx+10h]
0x1800069e4  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x1800069eb  mov     edx, 11h
0x1800069f0  mov     r9d, 0C0000084h
0x1800069f6  call    WPP_SF_d
0x1800069fb  mov     ebx, 0D0000084h
0x180006a00  jmp     short loc_180006A3F
0x180006a02  mov     r9d, 80070490h
0x180006a08  mov     ebx, r9d
0x180006a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a12  lea     rax, WPP_GLOBAL_Control
0x180006a19  cmp     rcx, rax
0x180006a1c  jz      short loc_180006A3F
0x180006a1e  test    byte ptr [rcx+1Ch], 80h
0x180006a22  jz      short loc_180006A3F
0x180006a24  cmp     byte ptr [rcx+19h], 2
0x180006a28  jb      short loc_180006A3F
0x180006a2a  mov     rcx, [rcx+10h]
0x180006a2e  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x180006a35  mov     edx, 10h
0x180006a3a  call    WPP_SF_d
0x180006a3f  mov     rcx, rdi; Block
0x180006a42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006a47  jmp     short loc_180006A86
0x180006a49  mov     r9d, 80070490h
0x180006a4f  mov     ebx, r9d
0x180006a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a59  lea     rax, WPP_GLOBAL_Control
0x180006a60  cmp     rcx, rax
0x180006a63  jz      short loc_180006A86
0x180006a65  test    byte ptr [rcx+1Ch], 80h
0x180006a69  jz      short loc_180006A86
0x180006a6b  cmp     byte ptr [rcx+19h], 2
0x180006a6f  jb      short loc_180006A86
0x180006a71  mov     edx, 0Eh
0x180006a76  mov     rcx, [rcx+10h]
0x180006a7a  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x180006a81  call    WPP_SF_d
0x180006a86  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180006a8b  test    rcx, rcx
0x180006a8e  jz      short loc_180006A96
0x180006a90  call    cs:__imp_CloseHandle
0x180006a96  test    rbp, rbp
0x180006a99  jz      short loc_180006AA4
0x180006a9b  mov     rcx, rbp; hObject
0x180006a9e  call    cs:__imp_CloseHandle
0x180006aa4  mov     rbp, [rsp+58h+arg_18]
0x180006aa9  mov     eax, ebx
0x180006aab  mov     rbx, [rsp+58h+arg_0]
0x180006ab0  add     rsp, 30h
0x180006ab4  pop     r15
0x180006ab6  pop     r14
0x180006ab8  pop     r12
0x180006aba  pop     rdi
0x180006abb  pop     rsi
0x180006abc  retn
```

# GetCardModuleHandle(_CARD_MATCH_DATA *,ushort *,HINSTANCE__ * *)

- ea: `0x180023504`
- end: `0x180023750`
- name: `?GetCardModuleHandle@@YAKPEAU_CARD_MATCH_DATA@@PEAGPEAPEAUHINSTANCE__@@@Z`
- size: `588`
- prototype: `unsigned int(struct _CARD_MATCH_DATA *, unsigned __int16 *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180023ed8`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x180023504`
- `0x18002896c`
- `0x180028c88`
- `0x18002bf00`
- `0x18002bf84`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800236da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800236da`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023606`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023621`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023606`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002362c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002362c`

## pseudocode

```c
__int64 __fastcall GetCardModuleHandle(LPCRITICAL_SECTION *a1, unsigned __int16 *a2, HINSTANCE *a3)
{
  __int64 result; // rax
  DWORD v7; // eax
  __int64 v8; // rsi
  DWORD LastError; // ebx
  HMODULE Library; // rax
  __int64 v11; // rcx
  HMODULE v12; // rcx
  int v13; // [rsp+20h] [rbp-78h]
  int v14; // [rsp+28h] [rbp-70h]
  __int64 v15; // [rsp+40h] [rbp-58h] BYREF
  __int64 v16; // [rsp+48h] [rbp-50h] BYREF
  __int128 v17; // [rsp+50h] [rbp-48h]

  v16 = 0;
  LODWORD(v15) = 0;
  v17 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  *a3 = 0;
  result = CspEnterCriticalSection(*a1);
  if ( !(_DWORD)result )
  {
    v7 = ScCacheRead(a1[1], v13, v14, (__int64)&v16, (__int64)&v15);
    v8 = v16;
    LastError = v7;
    if ( v7 + 2146434960 > 1 )
    {
      if ( !v7 )
      {
        if ( (_DWORD)v15 == 8 )
          *a3 = *(HINSTANCE *)v16;
        else
          LastError = -2146435041;
      }
      goto LABEL_20;
    }
    Library = LoadLibraryExW(a2, 0, 0);
    if ( Library || (Library = LoadLibraryExW(a2, 0, 0x1100u)) != 0 )
    {
      *a3 = Library;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
LABEL_20:
        CspLeaveCriticalSection(*a1);
        if ( LastError )
        {
          v12 = *a3;
          if ( *a3 )
          {
            FreeLibrary(v12);
            *a3 = 0;
          }
        }
        if ( v8 )
          CspFreeH(v8);
        WppTraceIndent(v12, 1);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
            (_DWORD)WPP_pszIndent,
            LastError);
        }
        return LastError;
      }
    }
    LastError = ScCacheWrite(a1[1], 0, 0, a3, 8);
    if ( LastError )
    {
      WppTraceIndent(v11, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          LastError);
      }
    }
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x180023504  push    rbx
0x180023506  push    rbp
0x180023507  push    rsi
0x180023508  push    rdi
0x180023509  push    r14
0x18002350b  sub     rsp, 70h
0x18002350f  mov     rax, cs:__security_cookie
0x180023516  xor     rax, rsp
0x180023519  mov     [rsp+98h+var_38], rax
0x18002351e  mov     rbp, rdx
0x180023521  mov     [rsp+98h+var_50], 0
0x18002352a  xorps   xmm0, xmm0
0x18002352d  mov     dword ptr [rsp+98h+var_58], 0
0x180023535  xor     edx, edx
0x180023537  mov     rdi, r8
0x18002353a  movups  [rsp+98h+var_48], xmm0
0x18002353f  mov     r14, rcx
0x180023542  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023547  mov     rcx, cs:WPP_GLOBAL_Control
0x18002354e  lea     rax, WPP_GLOBAL_Control
0x180023555  cmp     rcx, rax
0x180023558  jz      short loc_180023582
0x18002355a  test    byte ptr [rcx+1Ch], 2
0x18002355e  jz      short loc_180023582
0x180023560  cmp     byte ptr [rcx+19h], 5
0x180023564  jb      short loc_180023582
0x180023566  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002356d  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180023574  mov     rcx, [rcx+10h]
0x180023578  mov     edx, 0Ah
0x18002357d  call    WPP_SF_s
0x180023582  mov     qword ptr [rdi], 0
0x180023589  mov     rcx, [r14]
0x18002358c  call    CspEnterCriticalSection
0x180023591  test    eax, eax
0x180023593  jnz     loc_180023738
0x180023599  mov     rcx, [r14+8]; lpCriticalSection
0x18002359d  lea     rax, [rsp+98h+var_58]
0x1800235a2  mov     [rsp+98h+var_60], rax; __int64
0x1800235a7  lea     rdx, [rsp+98h+var_48]
0x1800235ac  lea     rax, [rsp+98h+var_50]
0x1800235b1  mov     r9, rbp
0x1800235b4  xor     r8d, r8d
0x1800235b7  mov     [rsp+98h+Src], rax; __int64
0x1800235bc  call    ScCacheRead
0x1800235c1  mov     rsi, [rsp+98h+var_50]
0x1800235c6  mov     ebx, eax
0x1800235c8  lea     ecx, [rax+7FEFFF90h]
0x1800235ce  cmp     ecx, 1
0x1800235d1  jbe     short loc_1800235FE
0x1800235d3  test    eax, eax
0x1800235d5  jnz     loc_1800236BF
0x1800235db  cmp     dword ptr [rsp+98h+var_58], 8
0x1800235e0  lea     rbp, WPP_GLOBAL_Control
0x1800235e7  jz      short loc_1800235F3
0x1800235e9  mov     ebx, 8010001Fh
0x1800235ee  jmp     loc_1800236C6
0x1800235f3  mov     rax, [rsi]
0x1800235f6  mov     [rdi], rax
0x1800235f9  jmp     loc_1800236C6
0x1800235fe  xor     r8d, r8d; dwFlags
0x180023601  xor     edx, edx; hFile
0x180023603  mov     rcx, rbp; lpLibFileName
0x180023606  call    cs:__imp_LoadLibraryExW
0x18002360c  test    rax, rax
0x18002360f  jz      short loc_180023616
0x180023611  mov     [rdi], rax
0x180023614  jmp     short loc_18002363C
0x180023616  xor     edx, edx; hFile
0x180023618  mov     r8d, 1100h; dwFlags
0x18002361e  mov     rcx, rbp; lpLibFileName
0x180023621  call    cs:__imp_LoadLibraryExW
0x180023627  test    rax, rax
0x18002362a  jnz     short loc_180023611
0x18002362c  call    cs:__imp_GetLastError
0x180023632  mov     ebx, eax
0x180023634  test    eax, eax
0x180023636  jnz     loc_1800236BF
0x18002363c  mov     rcx, [r14+8]; lpCriticalSection
0x180023640  lea     rdx, [rsp+98h+var_48]
0x180023645  mov     dword ptr [rsp+98h+var_60], 8; int
0x18002364d  mov     r9, rbp
0x180023650  mov     [rsp+98h+Src], rdi; Src
0x180023655  xor     r8d, r8d
0x180023658  mov     qword ptr [rsp+98h+var_70], 0; int
0x180023661  mov     [rsp+98h+var_78], 0; int
0x180023669  call    ScCacheWrite
0x18002366e  mov     ebx, eax
0x180023670  test    eax, eax
0x180023672  jz      short loc_1800236BF
0x180023674  mov     edx, 2
0x180023679  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002367e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023685  lea     rbp, WPP_GLOBAL_Control
0x18002368c  cmp     rcx, rbp
0x18002368f  jz      short loc_1800236C6
0x180023691  test    byte ptr [rcx+1Ch], 1
0x180023695  jz      short loc_1800236C6
0x180023697  cmp     byte ptr [rcx+19h], 2
0x18002369b  jb      short loc_1800236C6
0x18002369d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800236a4  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800236ab  mov     rcx, [rcx+10h]
0x1800236af  mov     edx, 0Bh
0x1800236b4  mov     [rsp+98h+var_78], ebx
0x1800236b8  call    WPP_SF_sD
0x1800236bd  jmp     short loc_1800236C6
0x1800236bf  lea     rbp, WPP_GLOBAL_Control
0x1800236c6  mov     rcx, [r14]
0x1800236c9  call    CspLeaveCriticalSection
0x1800236ce  test    ebx, ebx
0x1800236d0  jz      short loc_1800236E7
0x1800236d2  mov     rcx, [rdi]; hLibModule
0x1800236d5  test    rcx, rcx
0x1800236d8  jz      short loc_1800236E7
0x1800236da  call    cs:__imp_FreeLibrary
0x1800236e0  mov     qword ptr [rdi], 0
0x1800236e7  test    rsi, rsi
0x1800236ea  jz      short loc_1800236F4
0x1800236ec  mov     rcx, rsi
0x1800236ef  call    CspFreeH
0x1800236f4  mov     edx, 1
0x1800236f9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800236fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180023705  cmp     rcx, rbp
0x180023708  jz      short loc_180023736
0x18002370a  test    byte ptr [rcx+1Ch], 2
0x18002370e  jz      short loc_180023736
0x180023710  cmp     byte ptr [rcx+19h], 5
0x180023714  jb      short loc_180023736
0x180023716  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002371d  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180023724  mov     rcx, [rcx+10h]
0x180023728  mov     edx, 0Ch
0x18002372d  mov     [rsp+98h+var_78], ebx
0x180023731  call    WPP_SF_sD
0x180023736  mov     eax, ebx
0x180023738  mov     rcx, [rsp+98h+var_38]
0x18002373d  xor     rcx, rsp; StackCookie
0x180023740  call    __security_check_cookie
0x180023745  add     rsp, 70h
0x180023749  pop     r14
0x18002374b  pop     rdi
0x18002374c  pop     rsi
0x18002374d  pop     rbp
0x18002374e  pop     rbx
0x18002374f  retn
```

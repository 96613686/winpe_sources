# GetUserSid

- ea: `0x180024d88`
- end: `0x180024f63`
- name: `GetUserSid`
- size: `475`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180002f80`
- `0x18001b860`
- `0x18001cd30`

## callees

- `0x180021000`
- `0x1800246f4`
- `0x18002470c`
- `0x180024990`
- `0x180024d88`
- `0x180025f98`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180024e4f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180024e4f`
- `rtutils!TracePrintfExA` at `0x180024f03`
- `rtutils!TracePrintfExA` at `0x180024f03`

## string_xrefs

- `0x180024ef7`: `GetUserSid: returning %d `

## pseudocode

```c
__int64 __fastcall GetUserSid(__int64 a1)
{
  LPCWSTR v2; // rdi
  unsigned int CurrentToken; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int SidFromToken; // eax
  LPCWSTR lpString; // [rsp+50h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 5000);
  }
  v2 = 0;
  lpString = 0;
  hObject = 0;
  CurrentToken = GetCurrentToken(&hObject);
  v4 = CurrentToken;
  if ( CurrentToken )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 30;
LABEL_10:
      v7 = CurrentToken;
LABEL_11:
      WPP_SF_d(v5[2], v6, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v7);
    }
  }
  else
  {
    SidFromToken = GetSidFromToken(hObject, (HGLOBAL *)&lpString);
    v4 = SidFromToken;
    if ( SidFromToken )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, SidFromToken);
      }
      v2 = lpString;
    }
    else
    {
      v2 = lpString;
      if ( (unsigned int)lstrlenW(lpString) < 0x9C4 )
      {
        CurrentToken = StringCchCopyWrapW(a1, 2500, v2);
        v4 = CurrentToken;
        if ( CurrentToken )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v6 = 32;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v4 = 603;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 31;
          v7 = 603;
          goto LABEL_11;
        }
      }
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserSid: returning %d ", v4);
  if ( hObject )
    CloseHandle(hObject);
  Free0(v2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180024d88  mov     [rsp+arg_0], rbx
0x180024d8d  mov     [rsp+arg_8], rsi
0x180024d92  push    rdi
0x180024d93  push    r14
0x180024d95  push    r15
0x180024d97  sub     rsp, 20h
0x180024d9b  mov     rsi, rcx
0x180024d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024da5  lea     r14, WPP_GLOBAL_Control
0x180024dac  lea     r15, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x180024db3  cmp     rcx, r14
0x180024db6  jz      short loc_180024DDB
0x180024db8  test    byte ptr [rcx+1Ch], 4
0x180024dbc  jz      short loc_180024DDB
0x180024dbe  cmp     byte ptr [rcx+19h], 6
0x180024dc2  jb      short loc_180024DDB
0x180024dc4  mov     rcx, [rcx+10h]
0x180024dc8  mov     edx, 1Dh
0x180024dcd  mov     r9d, 1388h
0x180024dd3  mov     r8, r15
0x180024dd6  call    WPP_SF_d
0x180024ddb  xor     edi, edi
0x180024ddd  lea     rcx, [rsp+38h+hObject]; TokenHandle
0x180024de2  mov     [rsp+38h+lpString], rdi
0x180024de7  mov     [rsp+38h+hObject], rdi
0x180024dec  call    GetCurrentToken
0x180024df1  mov     ebx, eax
0x180024df3  test    eax, eax
0x180024df5  jz      short loc_180024E32
0x180024df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180024dfe  cmp     rcx, r14
0x180024e01  jz      loc_180024EE9
0x180024e07  test    byte ptr [rcx+1Ch], 4
0x180024e0b  jz      loc_180024EE9
0x180024e11  cmp     byte ptr [rcx+19h], 2
0x180024e15  jb      loc_180024EE9
0x180024e1b  lea     edx, [rdi+1Eh]
0x180024e1e  mov     r9d, eax
0x180024e21  mov     rcx, [rcx+10h]
0x180024e25  mov     r8, r15
0x180024e28  call    WPP_SF_d
0x180024e2d  jmp     loc_180024EE9
0x180024e32  mov     rcx, [rsp+38h+hObject]; TokenHandle
0x180024e37  lea     rdx, [rsp+38h+lpString]
0x180024e3c  call    GetSidFromToken
0x180024e41  mov     ebx, eax
0x180024e43  test    eax, eax
0x180024e45  jnz     short loc_180024EB8
0x180024e47  mov     rdi, [rsp+38h+lpString]
0x180024e4c  mov     rcx, rdi; lpString
0x180024e4f  call    cs:__imp_lstrlenW
0x180024e55  mov     edx, 9C4h
0x180024e5a  cmp     eax, edx
0x180024e5c  jb      short loc_180024E85
0x180024e5e  mov     ebx, 25Bh
0x180024e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e6a  cmp     rcx, r14
0x180024e6d  jz      short loc_180024EE9
0x180024e6f  test    byte ptr [rcx+1Ch], 4
0x180024e73  jz      short loc_180024EE9
0x180024e75  cmp     byte ptr [rcx+19h], 2
0x180024e79  jb      short loc_180024EE9
0x180024e7b  mov     edx, 1Fh
0x180024e80  mov     r9d, ebx
0x180024e83  jmp     short loc_180024E21
0x180024e85  mov     r8, rdi
0x180024e88  mov     rcx, rsi
0x180024e8b  call    StringCchCopyWrapW
0x180024e90  mov     ebx, eax
0x180024e92  test    eax, eax
0x180024e94  jz      short loc_180024EE9
0x180024e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e9d  cmp     rcx, r14
0x180024ea0  jz      short loc_180024EE9
0x180024ea2  test    byte ptr [rcx+1Ch], 4
0x180024ea6  jz      short loc_180024EE9
0x180024ea8  cmp     byte ptr [rcx+19h], 2
0x180024eac  jb      short loc_180024EE9
0x180024eae  mov     edx, 20h ; ' '
0x180024eb3  jmp     loc_180024E1E
0x180024eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ebf  cmp     rcx, r14
0x180024ec2  jz      short loc_180024EE4
0x180024ec4  test    byte ptr [rcx+1Ch], 4
0x180024ec8  jz      short loc_180024EE4
0x180024eca  cmp     byte ptr [rcx+19h], 2
0x180024ece  jb      short loc_180024EE4
0x180024ed0  mov     rcx, [rcx+10h]
0x180024ed4  mov     edx, 21h ; '!'
0x180024ed9  mov     r9d, eax
0x180024edc  mov     r8, r15
0x180024edf  call    WPP_SF_d
0x180024ee4  mov     rdi, [rsp+38h+lpString]
0x180024ee9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024eef  cmp     ecx, 0FFFFFFFFh
0x180024ef2  jz      short loc_180024F09
0x180024ef4  mov     r9d, ebx
0x180024ef7  lea     r8, aGetusersidRetu; "GetUserSid: returning %d "
0x180024efe  mov     edx, 0Ch; dwFlags
0x180024f03  call    cs:__imp_TracePrintfExA
0x180024f09  mov     rcx, [rsp+38h+hObject]; hObject
0x180024f0e  test    rcx, rcx
0x180024f11  jz      short loc_180024F19
0x180024f13  call    cs:__imp_CloseHandle
0x180024f19  mov     rcx, rdi
0x180024f1c  call    Free0
0x180024f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f28  cmp     rcx, r14
0x180024f2b  jz      short loc_180024F4D
0x180024f2d  test    byte ptr [rcx+1Ch], 4
0x180024f31  jz      short loc_180024F4D
0x180024f33  cmp     byte ptr [rcx+19h], 6
0x180024f37  jb      short loc_180024F4D
0x180024f39  mov     rcx, [rcx+10h]
0x180024f3d  mov     edx, 22h ; '"'
0x180024f42  mov     r9d, ebx
0x180024f45  mov     r8, r15
0x180024f48  call    WPP_SF_d
0x180024f4d  mov     rsi, [rsp+38h+arg_8]
0x180024f52  mov     eax, ebx
0x180024f54  mov     rbx, [rsp+38h+arg_0]
0x180024f59  add     rsp, 20h
0x180024f5d  pop     r15
0x180024f5f  pop     r14
0x180024f61  pop     rdi
0x180024f62  retn
```

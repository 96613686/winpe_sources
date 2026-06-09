# CFaxArchiving::CreateArchiveFolder(ushort const *,int,_SECURITY_ATTRIBUTES *,int *)

- ea: `0x140006760`
- end: `0x14000694e`
- name: `?CreateArchiveFolder@CFaxArchiving@@AEAAKPEBGHPEAU_SECURITY_ATTRIBUTES@@PEAH@Z`
- size: `494`
- prototype: `__int64 __fastcall(CFaxArchiving *this, const unsigned __int16 *, int, struct _SECURITY_ATTRIBUTES *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140006954`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140006760`
- `0x14000b8f4`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006861`
- `KERNEL32!GetLastError` at `0x1400068aa`
- `KERNEL32!GetLastError` at `0x140006861`
- `KERNEL32!GetLastError` at `0x1400068aa`
- `KERNEL32!CreateDirectoryW` at `0x140006853`
- `KERNEL32!CreateDirectoryW` at `0x140006853`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFaxArchiving::CreateArchiveFolder(
        CFaxArchiving *this,
        const unsigned __int16 *a2,
        int a3,
        struct _SECURITY_ATTRIBUTES *a4,
        int *a5)
{
  const wchar_t *v8; // rax
  int v9; // eax
  DWORD v10; // ebx
  DWORD LastError; // eax
  CFaxArchiving *v12; // rcx
  DWORD v13; // eax
  int v14; // eax
  WCHAR PathName[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  v8 = L"SentItems";
  if ( !a3 )
    v8 = L"Inbox";
  v9 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", a2, v8);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        238,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v9);
    }
    if ( (v10 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v10;
    return v10;
  }
  if ( CreateDirectoryW(PathName, a4) )
  {
    v14 = 1;
LABEL_31:
    v10 = 0;
    if ( *a5 )
      *a5 = v14;
    return v10;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError == 183 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, PathName);
    }
    if ( !CFaxArchiving::IsAccessibleFolder(v12, PathName) )
    {
      v13 = GetLastError();
      v10 = v13;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v13);
      }
      return v10;
    }
    v14 = 0;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      241,
      (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
      (unsigned int)PathName,
      LastError);
  }
  return v10;
}

```

## disassembly

```asm
0x140006760  mov     [rsp+arg_0], rbx
0x140006765  push    rbp
0x140006766  push    rsi
0x140006767  push    rdi
0x140006768  push    r12
0x14000676a  push    r15
0x14000676c  sub     rsp, 250h
0x140006773  mov     rax, cs:__security_cookie
0x14000677a  xor     rax, rsp
0x14000677d  mov     [rsp+278h+var_38], rax
0x140006785  mov     rdi, [rsp+278h+arg_20]
0x14000678d  mov     rsi, r9
0x140006790  mov     ebx, r8d
0x140006793  mov     rbp, rdx
0x140006796  mov     rcx, cs:WPP_GLOBAL_Control
0x14000679d  lea     r15, WPP_GLOBAL_Control
0x1400067a4  lea     r12, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400067ab  cmp     rcx, r15
0x1400067ae  jz      short loc_1400067CD
0x1400067b0  test    byte ptr [rcx+1Ch], 4
0x1400067b4  jz      short loc_1400067CD
0x1400067b6  cmp     byte ptr [rcx+19h], 5
0x1400067ba  jb      short loc_1400067CD
0x1400067bc  mov     rcx, [rcx+10h]
0x1400067c0  mov     edx, 0EDh
0x1400067c5  mov     r8, r12
0x1400067c8  call    WPP_SF_
0x1400067cd  lea     rcx, aInbox; "Inbox"
0x1400067d4  test    ebx, ebx
0x1400067d6  lea     rax, aSentitems; "SentItems"
0x1400067dd  mov     r9, rbp
0x1400067e0  cmovz   rax, rcx
0x1400067e4  lea     r8, aSS_0; "%s\\%s"
0x1400067eb  lea     rcx, [rsp+278h+PathName]; unsigned __int16 *
0x1400067f0  mov     [rsp+278h+var_258], rax
0x1400067f5  mov     edx, 104h; unsigned __int64
0x1400067fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400067ff  mov     ebx, eax
0x140006801  test    eax, eax
0x140006803  jns     short loc_14000684B
0x140006805  mov     rcx, cs:WPP_GLOBAL_Control
0x14000680c  cmp     rcx, r15
0x14000680f  jz      short loc_140006831
0x140006811  test    byte ptr [rcx+1Ch], 4
0x140006815  jz      short loc_140006831
0x140006817  cmp     byte ptr [rcx+19h], 2
0x14000681b  jb      short loc_140006831
0x14000681d  mov     rcx, [rcx+10h]
0x140006821  mov     edx, 0EEh
0x140006826  mov     r9d, eax
0x140006829  mov     r8, r12
0x14000682c  call    WPP_SF_d
0x140006831  mov     eax, ebx
0x140006833  and     eax, 1FFF0000h
0x140006838  cmp     eax, 70000h
0x14000683d  jnz     loc_140006925
0x140006843  movzx   ebx, bx
0x140006846  jmp     loc_140006925
0x14000684b  mov     rdx, rsi; lpSecurityAttributes
0x14000684e  lea     rcx, [rsp+278h+PathName]; lpPathName
0x140006853  call    cs:__imp_CreateDirectoryW
0x140006859  test    eax, eax
0x14000685b  jnz     loc_140006918
0x140006861  call    cs:__imp_GetLastError
0x140006867  mov     ebx, eax
0x140006869  cmp     eax, 0B7h
0x14000686e  jnz     short loc_1400068E4
0x140006870  mov     rcx, cs:WPP_GLOBAL_Control
0x140006877  cmp     rcx, r15
0x14000687a  jz      short loc_14000689C
0x14000687c  test    byte ptr [rcx+1Ch], 4
0x140006880  jz      short loc_14000689C
0x140006882  cmp     byte ptr [rcx+19h], 5
0x140006886  jb      short loc_14000689C
0x140006888  mov     rcx, [rcx+10h]
0x14000688c  lea     edx, [rax+38h]
0x14000688f  lea     r9, [rsp+278h+PathName]
0x140006894  mov     r8, r12
0x140006897  call    WPP_SF_S
0x14000689c  lea     rdx, [rsp+278h+PathName]; unsigned __int16 *
0x1400068a1  call    ?IsAccessibleFolder@CFaxArchiving@@AEAAHPEBG@Z; CFaxArchiving::IsAccessibleFolder(ushort const *)
0x1400068a6  test    eax, eax
0x1400068a8  jnz     short loc_1400068E0
0x1400068aa  call    cs:__imp_GetLastError
0x1400068b0  mov     ebx, eax
0x1400068b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068b9  cmp     rcx, r15
0x1400068bc  jz      short loc_140006925
0x1400068be  test    byte ptr [rcx+1Ch], 4
0x1400068c2  jz      short loc_140006925
0x1400068c4  cmp     byte ptr [rcx+19h], 2
0x1400068c8  jb      short loc_140006925
0x1400068ca  mov     rcx, [rcx+10h]
0x1400068ce  mov     edx, 0F0h
0x1400068d3  mov     r9d, eax
0x1400068d6  mov     r8, r12
0x1400068d9  call    WPP_SF_d
0x1400068de  jmp     short loc_140006925
0x1400068e0  xor     eax, eax
0x1400068e2  jmp     short loc_14000691D
0x1400068e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068eb  cmp     rcx, r15
0x1400068ee  jz      short loc_140006925
0x1400068f0  test    byte ptr [rcx+1Ch], 4
0x1400068f4  jz      short loc_140006925
0x1400068f6  cmp     byte ptr [rcx+19h], 2
0x1400068fa  jb      short loc_140006925
0x1400068fc  mov     rcx, [rcx+10h]
0x140006900  lea     r9, [rsp+278h+PathName]
0x140006905  mov     edx, 0F1h
0x14000690a  mov     dword ptr [rsp+278h+var_258], eax
0x14000690e  mov     r8, r12
0x140006911  call    WPP_SF_Sd
0x140006916  jmp     short loc_140006925
0x140006918  mov     eax, 1
0x14000691d  xor     ebx, ebx
0x14000691f  cmp     [rdi], ebx
0x140006921  jz      short loc_140006925
0x140006923  mov     [rdi], eax
0x140006925  mov     eax, ebx
0x140006927  mov     rcx, [rsp+278h+var_38]
0x14000692f  xor     rcx, rsp; StackCookie
0x140006932  call    __security_check_cookie
0x140006937  mov     rbx, [rsp+278h+arg_0]
0x14000693f  add     rsp, 250h
0x140006946  pop     r15
0x140006948  pop     r12
0x14000694a  pop     rdi
0x14000694b  pop     rsi
0x14000694c  pop     rbp
0x14000694d  retn
```

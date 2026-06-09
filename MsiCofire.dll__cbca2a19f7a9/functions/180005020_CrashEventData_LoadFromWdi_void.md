# CrashEventData::LoadFromWdi(void *)

- ea: `0x180005020`
- end: `0x180005407`
- name: `?LoadFromWdi@CrashEventData@@QEAAJPEAX@Z`
- size: `999`
- prototype: `__int64 __fastcall(CrashEventData *__hidden this, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180002770`
- `0x1800036f0`
- `0x180003ac8`

## callees

- `0x180002590`
- `0x180004f1c`
- `0x180005020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800050af`
- `KERNEL32!GetLastError` at `0x180005196`
- `KERNEL32!GetLastError` at `0x180005321`
- `KERNEL32!GetLastError` at `0x1800050af`
- `KERNEL32!GetLastError` at `0x180005196`
- `KERNEL32!GetLastError` at `0x180005321`
- `KERNEL32!HeapAlloc` at `0x1800050f4`
- `KERNEL32!HeapAlloc` at `0x1800051d5`
- `KERNEL32!HeapAlloc` at `0x180005356`
- `KERNEL32!HeapAlloc` at `0x1800050f4`
- `KERNEL32!HeapAlloc` at `0x1800051d5`
- `KERNEL32!HeapAlloc` at `0x180005356`
- `KERNEL32!GetProcessHeap` at `0x1800050e5`
- `KERNEL32!GetProcessHeap` at `0x1800051c6`
- `KERNEL32!GetProcessHeap` at `0x180005348`
- `KERNEL32!GetProcessHeap` at `0x1800050e5`
- `KERNEL32!GetProcessHeap` at `0x1800051c6`
- `KERNEL32!GetProcessHeap` at `0x180005348`
- `wdi!WdiGetParameterByName` at `0x180005072`
- `wdi!WdiGetParameterByName` at `0x180005159`
- `wdi!WdiGetParameterByName` at `0x18000523c`
- `wdi!WdiGetParameterByName` at `0x180005290`
- `wdi!WdiGetParameterByName` at `0x1800052e4`
- `wdi!WdiGetParameterByName` at `0x1800053ab`
- `wdi!WdiGetParameterByName` at `0x180005072`
- `wdi!WdiGetParameterByName` at `0x180005159`
- `wdi!WdiGetParameterByName` at `0x18000523c`
- `wdi!WdiGetParameterByName` at `0x180005290`
- `wdi!WdiGetParameterByName` at `0x1800052e4`
- `wdi!WdiGetParameterByName` at `0x1800053ab`
- `wdi!WdiGetParameterDataLength` at `0x180005091`
- `wdi!WdiGetParameterDataLength` at `0x180005178`
- `wdi!WdiGetParameterDataLength` at `0x180005303`
- `wdi!WdiGetParameterDataLength` at `0x180005091`
- `wdi!WdiGetParameterDataLength` at `0x180005178`
- `wdi!WdiGetParameterDataLength` at `0x180005303`
- `wdi!WdiGetParameterData` at `0x18000511f`
- `wdi!WdiGetParameterData` at `0x180005201`
- `wdi!WdiGetParameterData` at `0x180005261`
- `wdi!WdiGetParameterData` at `0x1800052b5`
- `wdi!WdiGetParameterData` at `0x18000537f`
- `wdi!WdiGetParameterData` at `0x1800053cd`
- `wdi!WdiGetParameterData` at `0x18000511f`
- `wdi!WdiGetParameterData` at `0x180005201`
- `wdi!WdiGetParameterData` at `0x180005261`
- `wdi!WdiGetParameterData` at `0x1800052b5`
- `wdi!WdiGetParameterData` at `0x18000537f`
- `wdi!WdiGetParameterData` at `0x1800053cd`

## string_xrefs

- `0x1800053ec`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x180005068`: `CorruptedFilePath`
- `0x1800052d8`: `UserSID`

## pseudocode

```c
__int64 __fastcall CrashEventData::LoadFromWdi(CrashEventData *this, void *a2)
{
  unsigned int v4; // ebx
  int ParameterByName; // eax
  int v6; // r9d
  signed int LastError; // eax
  __int64 v8; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v10; // rax
  signed int v11; // eax
  __int64 v12; // rbx
  HANDLE v13; // rax
  LPVOID v14; // rax
  signed int v15; // eax
  SIZE_T v16; // rbx
  HANDLE v17; // rax
  LPVOID v18; // rax
  SIZE_T dwBytes; // [rsp+58h] [rbp+28h] BYREF
  __int64 v21; // [rsp+60h] [rbp+30h] BYREF

  if ( !a2 )
  {
    v4 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "CrashEventData::LoadFromWdi", 188, -2147024809);
    return v4;
  }
  v21 = 0;
  LODWORD(dwBytes) = 0;
  CrashEventData::Free(this);
  ParameterByName = WdiGetParameterByName(a2, 0, L"CorruptedFilePath", &v21);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 203;
    goto LABEL_54;
  }
  ParameterByName = WdiGetParameterDataLength(v21, &dwBytes);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 208;
    goto LABEL_54;
  }
  if ( !(_DWORD)dwBytes )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "CrashEventData::LoadFromWdi", 209, v4);
    return v4;
  }
  if ( (unsigned int)dwBytes < 2 )
    return (unsigned int)-2147418113;
  v8 = (unsigned int)dwBytes;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, v8 + 2);
  *(_QWORD *)this = v10;
  if ( !v10 )
  {
    ParameterByName = -2147024882;
    v6 = 217;
    v4 = -2147024882;
    goto LABEL_54;
  }
  ParameterByName = WdiGetParameterData(v21, v10, (unsigned int)dwBytes);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 223;
    goto LABEL_54;
  }
  *(_WORD *)(*(_QWORD *)this + 2 * ((unsigned __int64)(unsigned int)dwBytes >> 1)) = 0;
  v21 = 0;
  ParameterByName = WdiGetParameterByName(a2, 0, L"CrashedAppName", &v21);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 236;
    goto LABEL_54;
  }
  ParameterByName = WdiGetParameterDataLength(v21, &dwBytes);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 241;
    goto LABEL_54;
  }
  if ( (_DWORD)dwBytes )
  {
    if ( (unsigned int)dwBytes < 2 )
      return (unsigned int)-2147418113;
    v12 = (unsigned int)dwBytes;
    v13 = GetProcessHeap();
    v14 = HeapAlloc(v13, 0, v12 + 2);
    *((_QWORD *)this + 1) = v14;
    if ( !v14 )
    {
      ParameterByName = -2147024882;
      v6 = 250;
      v4 = -2147024882;
      goto LABEL_54;
    }
    ParameterByName = WdiGetParameterData(v21, v14, (unsigned int)dwBytes);
    v4 = ParameterByName;
    if ( ParameterByName < 0 )
    {
      v6 = 256;
      goto LABEL_54;
    }
    *(_WORD *)(*((_QWORD *)this + 1) + 2 * ((unsigned __int64)(unsigned int)dwBytes >> 1)) = 0;
    v21 = 0;
    ParameterByName = WdiGetParameterByName(a2, 0, L"ExceptionCode", &v21);
    v4 = ParameterByName;
    if ( ParameterByName < 0 )
    {
      v6 = 268;
      goto LABEL_54;
    }
    ParameterByName = WdiGetParameterData(v21, (char *)this + 16, 4);
    v4 = ParameterByName;
    if ( ParameterByName < 0 )
    {
      v6 = 274;
      goto LABEL_54;
    }
    v21 = 0;
    ParameterByName = WdiGetParameterByName(a2, 0, L"ExceptionStatusCode", &v21);
    v4 = ParameterByName;
    if ( ParameterByName < 0 )
    {
      v6 = 284;
      goto LABEL_54;
    }
    ParameterByName = WdiGetParameterData(v21, (char *)this + 20, 4);
    v4 = ParameterByName;
    if ( ParameterByName < 0 )
    {
      v6 = 290;
      goto LABEL_54;
    }
    v21 = 0;
    ParameterByName = WdiGetParameterByName(a2, 0, L"UserSID", &v21);
    v4 = ParameterByName;
    if ( ParameterByName < 0 )
    {
      v6 = 300;
      goto LABEL_54;
    }
    ParameterByName = WdiGetParameterDataLength(v21, &dwBytes);
    v4 = ParameterByName;
    if ( ParameterByName < 0 )
    {
      v6 = 305;
      goto LABEL_54;
    }
    if ( (_DWORD)dwBytes )
    {
      v16 = (unsigned int)dwBytes;
      v17 = GetProcessHeap();
      v18 = HeapAlloc(v17, 0, v16);
      *((_QWORD *)this + 3) = v18;
      if ( v18 )
      {
        ParameterByName = WdiGetParameterData(v21, v18, (unsigned int)dwBytes);
        v4 = ParameterByName;
        if ( ParameterByName >= 0 )
        {
          v21 = 0;
          ParameterByName = WdiGetParameterByName(a2, 0, L"SessionID", &v21);
          v4 = ParameterByName;
          if ( ParameterByName >= 0 )
          {
            ParameterByName = WdiGetParameterData(v21, (char *)this + 32, 4);
            v4 = ParameterByName;
            if ( ParameterByName >= 0 )
              return v4;
            v6 = 330;
          }
          else
          {
            v6 = 324;
          }
        }
        else
        {
          v6 = 315;
        }
      }
      else
      {
        ParameterByName = -2147024882;
        v6 = 309;
        v4 = -2147024882;
      }
LABEL_54:
      DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "CrashEventData::LoadFromWdi", v6, ParameterByName);
      return v4;
    }
    v15 = GetLastError();
    v4 = v15;
    if ( v15 > 0 )
      v4 = (unsigned __int16)v15 | 0x80070000;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "CrashEventData::LoadFromWdi", 306, v4);
  }
  else
  {
    v11 = GetLastError();
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "CrashEventData::LoadFromWdi", 242, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180005020  mov     [rsp-18h+arg_0], rbx
0x180005025  push    rbp
0x180005026  push    rsi
0x180005027  push    rdi
0x180005028  mov     rbp, rsp
0x18000502b  sub     rsp, 30h
0x18000502f  mov     rsi, rdx
0x180005032  mov     rdi, rcx
0x180005035  test    rdx, rdx
0x180005038  jnz     short loc_18000504E
0x18000503a  mov     ebx, 80070057h
0x18000503f  mov     r9d, 0BCh
0x180005045  mov     [rsp+30h+var_10], ebx
0x180005049  jmp     loc_1800053E3
0x18000504e  mov     [rbp+arg_10], 0
0x180005056  mov     dword ptr [rbp+dwBytes], 0
0x18000505d  call    ?Free@CrashEventData@@QEAAXXZ; CrashEventData::Free(void)
0x180005062  lea     r9, [rbp+arg_10]
0x180005066  xor     edx, edx
0x180005068  lea     r8, aCorruptedfilep; "CorruptedFilePath"
0x18000506f  mov     rcx, rsi
0x180005072  call    cs:__imp_WdiGetParameterByName
0x180005078  mov     ebx, eax
0x18000507a  test    eax, eax
0x18000507c  jns     short loc_180005089
0x18000507e  mov     r9d, 0CBh
0x180005084  jmp     loc_1800053DF
0x180005089  mov     rcx, [rbp+arg_10]
0x18000508d  lea     rdx, [rbp+dwBytes]
0x180005091  call    cs:__imp_WdiGetParameterDataLength
0x180005097  mov     ebx, eax
0x180005099  test    eax, eax
0x18000509b  jns     short loc_1800050A8
0x18000509d  mov     r9d, 0D0h
0x1800050a3  jmp     loc_1800053DF
0x1800050a8  mov     eax, dword ptr [rbp+dwBytes]
0x1800050ab  test    eax, eax
0x1800050ad  jnz     short loc_1800050D3
0x1800050af  call    cs:__imp_GetLastError
0x1800050b5  mov     ebx, eax
0x1800050b7  test    eax, eax
0x1800050b9  jle     short loc_1800050C4
0x1800050bb  movzx   ebx, ax
0x1800050be  or      ebx, 80070000h
0x1800050c4  mov     [rsp+30h+var_10], ebx
0x1800050c8  mov     r9d, 0D1h
0x1800050ce  jmp     loc_1800053E3
0x1800050d3  cmp     eax, 2
0x1800050d6  jnb     short loc_1800050E2
0x1800050d8  mov     ebx, 8000FFFFh
0x1800050dd  jmp     loc_1800053F8
0x1800050e2  mov     rbx, rax
0x1800050e5  call    cs:__imp_GetProcessHeap
0x1800050eb  lea     r8, [rbx+2]; dwBytes
0x1800050ef  xor     edx, edx; dwFlags
0x1800050f1  mov     rcx, rax; hHeap
0x1800050f4  call    cs:__imp_HeapAlloc
0x1800050fa  mov     [rdi], rax
0x1800050fd  test    rax, rax
0x180005100  jnz     short loc_180005114
0x180005102  mov     eax, 8007000Eh
0x180005107  mov     r9d, 0D9h
0x18000510d  mov     ebx, eax
0x18000510f  jmp     loc_1800053DF
0x180005114  mov     r8d, dword ptr [rbp+dwBytes]
0x180005118  mov     rdx, rax
0x18000511b  mov     rcx, [rbp+arg_10]
0x18000511f  call    cs:__imp_WdiGetParameterData
0x180005125  mov     ebx, eax
0x180005127  test    eax, eax
0x180005129  jns     short loc_180005136
0x18000512b  mov     r9d, 0DFh
0x180005131  jmp     loc_1800053DF
0x180005136  mov     edx, dword ptr [rbp+dwBytes]
0x180005139  lea     r9, [rbp+arg_10]
0x18000513d  mov     rcx, [rdi]
0x180005140  lea     r8, aCrashedappname; "CrashedAppName"
0x180005147  shr     rdx, 1
0x18000514a  xor     eax, eax
0x18000514c  mov     [rcx+rdx*2], ax
0x180005150  xor     edx, edx
0x180005152  mov     rcx, rsi
0x180005155  mov     [rbp+arg_10], rax
0x180005159  call    cs:__imp_WdiGetParameterByName
0x18000515f  mov     ebx, eax
0x180005161  test    eax, eax
0x180005163  jns     short loc_180005170
0x180005165  mov     r9d, 0ECh
0x18000516b  jmp     loc_1800053DF
0x180005170  mov     rcx, [rbp+arg_10]
0x180005174  lea     rdx, [rbp+dwBytes]
0x180005178  call    cs:__imp_WdiGetParameterDataLength
0x18000517e  mov     ebx, eax
0x180005180  test    eax, eax
0x180005182  jns     short loc_18000518F
0x180005184  mov     r9d, 0F1h
0x18000518a  jmp     loc_1800053DF
0x18000518f  mov     eax, dword ptr [rbp+dwBytes]
0x180005192  test    eax, eax
0x180005194  jnz     short loc_1800051BA
0x180005196  call    cs:__imp_GetLastError
0x18000519c  mov     ebx, eax
0x18000519e  test    eax, eax
0x1800051a0  jle     short loc_1800051AB
0x1800051a2  movzx   ebx, ax
0x1800051a5  or      ebx, 80070000h
0x1800051ab  mov     [rsp+30h+var_10], ebx
0x1800051af  mov     r9d, 0F2h
0x1800051b5  jmp     loc_1800053E3
0x1800051ba  cmp     eax, 2
0x1800051bd  jb      loc_1800050D8
0x1800051c3  mov     rbx, rax
0x1800051c6  call    cs:__imp_GetProcessHeap
0x1800051cc  lea     r8, [rbx+2]; dwBytes
0x1800051d0  xor     edx, edx; dwFlags
0x1800051d2  mov     rcx, rax; hHeap
0x1800051d5  call    cs:__imp_HeapAlloc
0x1800051db  mov     [rdi+8], rax
0x1800051df  test    rax, rax
0x1800051e2  jnz     short loc_1800051F6
0x1800051e4  mov     eax, 8007000Eh
0x1800051e9  mov     r9d, 0FAh
0x1800051ef  mov     ebx, eax
0x1800051f1  jmp     loc_1800053DF
0x1800051f6  mov     r8d, dword ptr [rbp+dwBytes]
0x1800051fa  mov     rdx, rax
0x1800051fd  mov     rcx, [rbp+arg_10]
0x180005201  call    cs:__imp_WdiGetParameterData
0x180005207  mov     ebx, eax
0x180005209  test    eax, eax
0x18000520b  jns     short loc_180005218
0x18000520d  mov     r9d, 100h
0x180005213  jmp     loc_1800053DF
0x180005218  mov     edx, dword ptr [rbp+dwBytes]
0x18000521b  lea     r9, [rbp+arg_10]
0x18000521f  mov     rcx, [rdi+8]
0x180005223  lea     r8, aExceptioncode; "ExceptionCode"
0x18000522a  shr     rdx, 1
0x18000522d  xor     eax, eax
0x18000522f  mov     [rcx+rdx*2], ax
0x180005233  xor     edx, edx
0x180005235  mov     rcx, rsi
0x180005238  mov     [rbp+arg_10], rax
0x18000523c  call    cs:__imp_WdiGetParameterByName
0x180005242  mov     ebx, eax
0x180005244  test    eax, eax
0x180005246  jns     short loc_180005253
0x180005248  mov     r9d, 10Ch
0x18000524e  jmp     loc_1800053DF
0x180005253  mov     rcx, [rbp+arg_10]
0x180005257  lea     rdx, [rdi+10h]
0x18000525b  mov     r8d, 4
0x180005261  call    cs:__imp_WdiGetParameterData
0x180005267  mov     ebx, eax
0x180005269  test    eax, eax
0x18000526b  jns     short loc_180005278
0x18000526d  mov     r9d, 112h
0x180005273  jmp     loc_1800053DF
0x180005278  lea     r9, [rbp+arg_10]
0x18000527c  mov     [rbp+arg_10], 0
0x180005284  lea     r8, aExceptionstatu; "ExceptionStatusCode"
0x18000528b  xor     edx, edx
0x18000528d  mov     rcx, rsi
0x180005290  call    cs:__imp_WdiGetParameterByName
0x180005296  mov     ebx, eax
0x180005298  test    eax, eax
0x18000529a  jns     short loc_1800052A7
0x18000529c  mov     r9d, 11Ch
0x1800052a2  jmp     loc_1800053DF
0x1800052a7  mov     rcx, [rbp+arg_10]
0x1800052ab  lea     rdx, [rdi+14h]
0x1800052af  mov     r8d, 4
0x1800052b5  call    cs:__imp_WdiGetParameterData
0x1800052bb  mov     ebx, eax
0x1800052bd  test    eax, eax
0x1800052bf  jns     short loc_1800052CC
0x1800052c1  mov     r9d, 122h
0x1800052c7  jmp     loc_1800053DF
0x1800052cc  lea     r9, [rbp+arg_10]
0x1800052d0  mov     [rbp+arg_10], 0
0x1800052d8  lea     r8, aUsersid; "UserSID"
0x1800052df  xor     edx, edx
0x1800052e1  mov     rcx, rsi
0x1800052e4  call    cs:__imp_WdiGetParameterByName
0x1800052ea  mov     ebx, eax
0x1800052ec  test    eax, eax
0x1800052ee  jns     short loc_1800052FB
0x1800052f0  mov     r9d, 12Ch
0x1800052f6  jmp     loc_1800053DF
0x1800052fb  mov     rcx, [rbp+arg_10]
0x1800052ff  lea     rdx, [rbp+dwBytes]
0x180005303  call    cs:__imp_WdiGetParameterDataLength
0x180005309  mov     ebx, eax
0x18000530b  test    eax, eax
0x18000530d  jns     short loc_18000531A
0x18000530f  mov     r9d, 131h
0x180005315  jmp     loc_1800053DF
0x18000531a  mov     eax, dword ptr [rbp+dwBytes]
0x18000531d  test    eax, eax
0x18000531f  jnz     short loc_180005345
0x180005321  call    cs:__imp_GetLastError
0x180005327  mov     ebx, eax
0x180005329  test    eax, eax
0x18000532b  jle     short loc_180005336
0x18000532d  movzx   ebx, ax
0x180005330  or      ebx, 80070000h
0x180005336  mov     [rsp+30h+var_10], ebx
0x18000533a  mov     r9d, 132h
0x180005340  jmp     loc_1800053E3
0x180005345  mov     rbx, rax
0x180005348  call    cs:__imp_GetProcessHeap
0x18000534e  mov     r8, rbx; dwBytes
0x180005351  xor     edx, edx; dwFlags
0x180005353  mov     rcx, rax; hHeap
0x180005356  call    cs:__imp_HeapAlloc
0x18000535c  mov     [rdi+18h], rax
0x180005360  test    rax, rax
0x180005363  jnz     short loc_180005374
0x180005365  mov     eax, 8007000Eh
0x18000536a  mov     r9d, 135h
0x180005370  mov     ebx, eax
0x180005372  jmp     short loc_1800053DF
0x180005374  mov     r8d, dword ptr [rbp+dwBytes]
0x180005378  mov     rdx, rax
0x18000537b  mov     rcx, [rbp+arg_10]
0x18000537f  call    cs:__imp_WdiGetParameterData
0x180005385  mov     ebx, eax
0x180005387  test    eax, eax
0x180005389  jns     short loc_180005393
0x18000538b  mov     r9d, 13Bh
0x180005391  jmp     short loc_1800053DF
0x180005393  lea     r9, [rbp+arg_10]
0x180005397  mov     [rbp+arg_10], 0
0x18000539f  lea     r8, aSessionid; "SessionID"
0x1800053a6  xor     edx, edx
0x1800053a8  mov     rcx, rsi
0x1800053ab  call    cs:__imp_WdiGetParameterByName
0x1800053b1  mov     ebx, eax
0x1800053b3  test    eax, eax
0x1800053b5  jns     short loc_1800053BF
0x1800053b7  mov     r9d, 144h
0x1800053bd  jmp     short loc_1800053DF
0x1800053bf  mov     rcx, [rbp+arg_10]
0x1800053c3  lea     rdx, [rdi+20h]
0x1800053c7  mov     r8d, 4
0x1800053cd  call    cs:__imp_WdiGetParameterData
0x1800053d3  mov     ebx, eax
0x1800053d5  test    eax, eax
0x1800053d7  jns     short loc_1800053F8
0x1800053d9  mov     r9d, 14Ah
0x1800053df  mov     [rsp+30h+var_10], eax
0x1800053e3  lea     r8, aCrasheventdata; "CrashEventData::LoadFromWdi"
0x1800053ea  xor     ecx, ecx; Level
0x1800053ec  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x1800053f3  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800053f8  mov     eax, ebx
0x1800053fa  mov     rbx, [rsp+30h+arg_0]
0x1800053ff  add     rsp, 30h
0x180005403  pop     rdi
0x180005404  pop     rsi
0x180005405  pop     rbp
0x180005406  retn
```

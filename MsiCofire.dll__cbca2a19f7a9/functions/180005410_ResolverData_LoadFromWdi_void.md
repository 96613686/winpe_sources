# ResolverData::LoadFromWdi(void *)

- ea: `0x180005410`
- end: `0x18000577e`
- name: `?LoadFromWdi@ResolverData@@QEAAJPEAX@Z`
- size: `878`
- prototype: `__int64 __fastcall(ResolverData *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800036f0`

## callees

- `0x180002590`
- `0x180004fa0`
- `0x180005410`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000549f`
- `KERNEL32!GetLastError` at `0x180005586`
- `KERNEL32!GetLastError` at `0x18000549f`
- `KERNEL32!GetLastError` at `0x180005586`
- `KERNEL32!HeapAlloc` at `0x1800054e4`
- `KERNEL32!HeapAlloc` at `0x1800055c5`
- `KERNEL32!HeapAlloc` at `0x1800054e4`
- `KERNEL32!HeapAlloc` at `0x1800055c5`
- `KERNEL32!GetProcessHeap` at `0x1800054d5`
- `KERNEL32!GetProcessHeap` at `0x1800055b6`
- `KERNEL32!GetProcessHeap` at `0x1800054d5`
- `KERNEL32!GetProcessHeap` at `0x1800055b6`
- `wdi!WdiGetParameterByName` at `0x180005462`
- `wdi!WdiGetParameterByName` at `0x180005549`
- `wdi!WdiGetParameterByName` at `0x18000562c`
- `wdi!WdiGetParameterByName` at `0x180005680`
- `wdi!WdiGetParameterByName` at `0x1800056d4`
- `wdi!WdiGetParameterByName` at `0x180005722`
- `wdi!WdiGetParameterByName` at `0x180005462`
- `wdi!WdiGetParameterByName` at `0x180005549`
- `wdi!WdiGetParameterByName` at `0x18000562c`
- `wdi!WdiGetParameterByName` at `0x180005680`
- `wdi!WdiGetParameterByName` at `0x1800056d4`
- `wdi!WdiGetParameterByName` at `0x180005722`
- `wdi!WdiGetParameterDataLength` at `0x180005481`
- `wdi!WdiGetParameterDataLength` at `0x180005568`
- `wdi!WdiGetParameterDataLength` at `0x180005481`
- `wdi!WdiGetParameterDataLength` at `0x180005568`
- `wdi!WdiGetParameterData` at `0x18000550f`
- `wdi!WdiGetParameterData` at `0x1800055f1`
- `wdi!WdiGetParameterData` at `0x180005651`
- `wdi!WdiGetParameterData` at `0x1800056a5`
- `wdi!WdiGetParameterData` at `0x1800056f6`
- `wdi!WdiGetParameterData` at `0x180005744`
- `wdi!WdiGetParameterData` at `0x18000550f`
- `wdi!WdiGetParameterData` at `0x1800055f1`
- `wdi!WdiGetParameterData` at `0x180005651`
- `wdi!WdiGetParameterData` at `0x1800056a5`
- `wdi!WdiGetParameterData` at `0x1800056f6`
- `wdi!WdiGetParameterData` at `0x180005744`

## string_xrefs

- `0x180005763`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall ResolverData::LoadFromWdi(ResolverData *this, void *a2)
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
  unsigned int v16; // [rsp+58h] [rbp+28h] BYREF
  __int64 v17; // [rsp+60h] [rbp+30h] BYREF

  if ( !a2 )
  {
    v4 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "ResolverData::LoadFromWdi", 428, -2147024809);
    return v4;
  }
  v17 = 0;
  v16 = 0;
  ResolverData::Free(this);
  ParameterByName = WdiGetParameterByName(a2, 0, L"ProductName", &v17);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 443;
    goto LABEL_46;
  }
  ParameterByName = WdiGetParameterDataLength(v17, &v16);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 448;
    goto LABEL_46;
  }
  if ( !v16 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "ResolverData::LoadFromWdi", 449, v4);
    return v4;
  }
  if ( v16 < 2 )
    return (unsigned int)-2147418113;
  v8 = v16;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, v8 + 2);
  *(_QWORD *)this = v10;
  if ( !v10 )
  {
    ParameterByName = -2147024882;
    v6 = 457;
    v4 = -2147024882;
    goto LABEL_46;
  }
  ParameterByName = WdiGetParameterData(v17, v10, v16);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 463;
    goto LABEL_46;
  }
  *(_WORD *)(*(_QWORD *)this + 2 * ((unsigned __int64)v16 >> 1)) = 0;
  v17 = 0;
  ParameterByName = WdiGetParameterByName(a2, 0, L"ProductVersion", &v17);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 475;
    goto LABEL_46;
  }
  ParameterByName = WdiGetParameterDataLength(v17, &v16);
  v4 = ParameterByName;
  if ( ParameterByName < 0 )
  {
    v6 = 480;
    goto LABEL_46;
  }
  if ( v16 )
  {
    if ( v16 >= 2 )
    {
      v12 = v16;
      v13 = GetProcessHeap();
      v14 = HeapAlloc(v13, 0, v12 + 2);
      *((_QWORD *)this + 1) = v14;
      if ( v14 )
      {
        ParameterByName = WdiGetParameterData(v17, v14, v16);
        v4 = ParameterByName;
        if ( ParameterByName >= 0 )
        {
          *(_WORD *)(*((_QWORD *)this + 1) + 2 * ((unsigned __int64)v16 >> 1)) = 0;
          v17 = 0;
          ParameterByName = WdiGetParameterByName(a2, 0, L"OnScreenTime", &v17);
          v4 = ParameterByName;
          if ( ParameterByName >= 0 )
          {
            ParameterByName = WdiGetParameterData(v17, (char *)this + 16, 4);
            v4 = ParameterByName;
            if ( ParameterByName >= 0 )
            {
              v17 = 0;
              ParameterByName = WdiGetParameterByName(a2, 0, L"UiUserAction", &v17);
              v4 = ParameterByName;
              if ( ParameterByName >= 0 )
              {
                ParameterByName = WdiGetParameterData(v17, (char *)this + 24, 4);
                v4 = ParameterByName;
                if ( ParameterByName >= 0 )
                {
                  v17 = 0;
                  ParameterByName = WdiGetParameterByName(a2, 0, L"ResolverResult", &v17);
                  v4 = ParameterByName;
                  if ( ParameterByName >= 0 )
                  {
                    ParameterByName = WdiGetParameterData(v17, (char *)this + 28, 4);
                    v4 = ParameterByName;
                    if ( ParameterByName >= 0 )
                    {
                      v17 = 0;
                      ParameterByName = WdiGetParameterByName(a2, 0, L"ResolverError", &v17);
                      v4 = ParameterByName;
                      if ( ParameterByName >= 0 )
                      {
                        ParameterByName = WdiGetParameterData(v17, (char *)this + 32, 4);
                        v4 = ParameterByName;
                        if ( ParameterByName >= 0 )
                          return v4;
                        v6 = 561;
                      }
                      else
                      {
                        v6 = 555;
                      }
                    }
                    else
                    {
                      v6 = 545;
                    }
                  }
                  else
                  {
                    v6 = 539;
                  }
                }
                else
                {
                  v6 = 529;
                }
              }
              else
              {
                v6 = 523;
              }
            }
            else
            {
              v6 = 513;
            }
          }
          else
          {
            v6 = 507;
          }
        }
        else
        {
          v6 = 495;
        }
      }
      else
      {
        ParameterByName = -2147024882;
        v6 = 489;
        v4 = -2147024882;
      }
LABEL_46:
      DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "ResolverData::LoadFromWdi", v6, ParameterByName);
      return v4;
    }
    return (unsigned int)-2147418113;
  }
  v11 = GetLastError();
  v4 = v11;
  if ( v11 > 0 )
    v4 = (unsigned __int16)v11 | 0x80070000;
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "ResolverData::LoadFromWdi", 481, v4);
  return v4;
}

```

## disassembly

```asm
0x180005410  mov     [rsp-18h+arg_0], rbx
0x180005415  push    rbp
0x180005416  push    rsi
0x180005417  push    rdi
0x180005418  mov     rbp, rsp
0x18000541b  sub     rsp, 30h
0x18000541f  mov     rsi, rdx
0x180005422  mov     rdi, rcx
0x180005425  test    rdx, rdx
0x180005428  jnz     short loc_18000543E
0x18000542a  mov     ebx, 80070057h
0x18000542f  mov     r9d, 1ACh
0x180005435  mov     [rsp+30h+var_10], ebx
0x180005439  jmp     loc_18000575A
0x18000543e  mov     [rbp+arg_10], 0
0x180005446  mov     [rbp+arg_8], 0
0x18000544d  call    ?Free@ResolverData@@QEAAXXZ; ResolverData::Free(void)
0x180005452  lea     r9, [rbp+arg_10]
0x180005456  xor     edx, edx
0x180005458  lea     r8, aProductname; "ProductName"
0x18000545f  mov     rcx, rsi
0x180005462  call    cs:__imp_WdiGetParameterByName
0x180005468  mov     ebx, eax
0x18000546a  test    eax, eax
0x18000546c  jns     short loc_180005479
0x18000546e  mov     r9d, 1BBh
0x180005474  jmp     loc_180005756
0x180005479  mov     rcx, [rbp+arg_10]
0x18000547d  lea     rdx, [rbp+arg_8]
0x180005481  call    cs:__imp_WdiGetParameterDataLength
0x180005487  mov     ebx, eax
0x180005489  test    eax, eax
0x18000548b  jns     short loc_180005498
0x18000548d  mov     r9d, 1C0h
0x180005493  jmp     loc_180005756
0x180005498  mov     eax, [rbp+arg_8]
0x18000549b  test    eax, eax
0x18000549d  jnz     short loc_1800054C3
0x18000549f  call    cs:__imp_GetLastError
0x1800054a5  mov     ebx, eax
0x1800054a7  test    eax, eax
0x1800054a9  jle     short loc_1800054B4
0x1800054ab  movzx   ebx, ax
0x1800054ae  or      ebx, 80070000h
0x1800054b4  mov     [rsp+30h+var_10], ebx
0x1800054b8  mov     r9d, 1C1h
0x1800054be  jmp     loc_18000575A
0x1800054c3  cmp     eax, 2
0x1800054c6  jnb     short loc_1800054D2
0x1800054c8  mov     ebx, 8000FFFFh
0x1800054cd  jmp     loc_18000576F
0x1800054d2  mov     rbx, rax
0x1800054d5  call    cs:__imp_GetProcessHeap
0x1800054db  lea     r8, [rbx+2]; dwBytes
0x1800054df  xor     edx, edx; dwFlags
0x1800054e1  mov     rcx, rax; hHeap
0x1800054e4  call    cs:__imp_HeapAlloc
0x1800054ea  mov     [rdi], rax
0x1800054ed  test    rax, rax
0x1800054f0  jnz     short loc_180005504
0x1800054f2  mov     eax, 8007000Eh
0x1800054f7  mov     r9d, 1C9h
0x1800054fd  mov     ebx, eax
0x1800054ff  jmp     loc_180005756
0x180005504  mov     r8d, [rbp+arg_8]
0x180005508  mov     rdx, rax
0x18000550b  mov     rcx, [rbp+arg_10]
0x18000550f  call    cs:__imp_WdiGetParameterData
0x180005515  mov     ebx, eax
0x180005517  test    eax, eax
0x180005519  jns     short loc_180005526
0x18000551b  mov     r9d, 1CFh
0x180005521  jmp     loc_180005756
0x180005526  mov     edx, [rbp+arg_8]
0x180005529  lea     r9, [rbp+arg_10]
0x18000552d  mov     rcx, [rdi]
0x180005530  lea     r8, aProductversion; "ProductVersion"
0x180005537  shr     rdx, 1
0x18000553a  xor     eax, eax
0x18000553c  mov     [rcx+rdx*2], ax
0x180005540  xor     edx, edx
0x180005542  mov     rcx, rsi
0x180005545  mov     [rbp+arg_10], rax
0x180005549  call    cs:__imp_WdiGetParameterByName
0x18000554f  mov     ebx, eax
0x180005551  test    eax, eax
0x180005553  jns     short loc_180005560
0x180005555  mov     r9d, 1DBh
0x18000555b  jmp     loc_180005756
0x180005560  mov     rcx, [rbp+arg_10]
0x180005564  lea     rdx, [rbp+arg_8]
0x180005568  call    cs:__imp_WdiGetParameterDataLength
0x18000556e  mov     ebx, eax
0x180005570  test    eax, eax
0x180005572  jns     short loc_18000557F
0x180005574  mov     r9d, 1E0h
0x18000557a  jmp     loc_180005756
0x18000557f  mov     eax, [rbp+arg_8]
0x180005582  test    eax, eax
0x180005584  jnz     short loc_1800055AA
0x180005586  call    cs:__imp_GetLastError
0x18000558c  mov     ebx, eax
0x18000558e  test    eax, eax
0x180005590  jle     short loc_18000559B
0x180005592  movzx   ebx, ax
0x180005595  or      ebx, 80070000h
0x18000559b  mov     [rsp+30h+var_10], ebx
0x18000559f  mov     r9d, 1E1h
0x1800055a5  jmp     loc_18000575A
0x1800055aa  cmp     eax, 2
0x1800055ad  jb      loc_1800054C8
0x1800055b3  mov     rbx, rax
0x1800055b6  call    cs:__imp_GetProcessHeap
0x1800055bc  lea     r8, [rbx+2]; dwBytes
0x1800055c0  xor     edx, edx; dwFlags
0x1800055c2  mov     rcx, rax; hHeap
0x1800055c5  call    cs:__imp_HeapAlloc
0x1800055cb  mov     [rdi+8], rax
0x1800055cf  test    rax, rax
0x1800055d2  jnz     short loc_1800055E6
0x1800055d4  mov     eax, 8007000Eh
0x1800055d9  mov     r9d, 1E9h
0x1800055df  mov     ebx, eax
0x1800055e1  jmp     loc_180005756
0x1800055e6  mov     r8d, [rbp+arg_8]
0x1800055ea  mov     rdx, rax
0x1800055ed  mov     rcx, [rbp+arg_10]
0x1800055f1  call    cs:__imp_WdiGetParameterData
0x1800055f7  mov     ebx, eax
0x1800055f9  test    eax, eax
0x1800055fb  jns     short loc_180005608
0x1800055fd  mov     r9d, 1EFh
0x180005603  jmp     loc_180005756
0x180005608  mov     edx, [rbp+arg_8]
0x18000560b  lea     r9, [rbp+arg_10]
0x18000560f  mov     rcx, [rdi+8]
0x180005613  lea     r8, aOnscreentime; "OnScreenTime"
0x18000561a  shr     rdx, 1
0x18000561d  xor     eax, eax
0x18000561f  mov     [rcx+rdx*2], ax
0x180005623  xor     edx, edx
0x180005625  mov     rcx, rsi
0x180005628  mov     [rbp+arg_10], rax
0x18000562c  call    cs:__imp_WdiGetParameterByName
0x180005632  mov     ebx, eax
0x180005634  test    eax, eax
0x180005636  jns     short loc_180005643
0x180005638  mov     r9d, 1FBh
0x18000563e  jmp     loc_180005756
0x180005643  mov     rcx, [rbp+arg_10]
0x180005647  lea     rdx, [rdi+10h]
0x18000564b  mov     r8d, 4
0x180005651  call    cs:__imp_WdiGetParameterData
0x180005657  mov     ebx, eax
0x180005659  test    eax, eax
0x18000565b  jns     short loc_180005668
0x18000565d  mov     r9d, 201h
0x180005663  jmp     loc_180005756
0x180005668  lea     r9, [rbp+arg_10]
0x18000566c  mov     [rbp+arg_10], 0
0x180005674  lea     r8, aUiuseraction; "UiUserAction"
0x18000567b  xor     edx, edx
0x18000567d  mov     rcx, rsi
0x180005680  call    cs:__imp_WdiGetParameterByName
0x180005686  mov     ebx, eax
0x180005688  test    eax, eax
0x18000568a  jns     short loc_180005697
0x18000568c  mov     r9d, 20Bh
0x180005692  jmp     loc_180005756
0x180005697  mov     rcx, [rbp+arg_10]
0x18000569b  lea     rdx, [rdi+18h]
0x18000569f  mov     r8d, 4
0x1800056a5  call    cs:__imp_WdiGetParameterData
0x1800056ab  mov     ebx, eax
0x1800056ad  test    eax, eax
0x1800056af  jns     short loc_1800056BC
0x1800056b1  mov     r9d, 211h
0x1800056b7  jmp     loc_180005756
0x1800056bc  lea     r9, [rbp+arg_10]
0x1800056c0  mov     [rbp+arg_10], 0
0x1800056c8  lea     r8, aResolverresult; "ResolverResult"
0x1800056cf  xor     edx, edx
0x1800056d1  mov     rcx, rsi
0x1800056d4  call    cs:__imp_WdiGetParameterByName
0x1800056da  mov     ebx, eax
0x1800056dc  test    eax, eax
0x1800056de  jns     short loc_1800056E8
0x1800056e0  mov     r9d, 21Bh
0x1800056e6  jmp     short loc_180005756
0x1800056e8  mov     rcx, [rbp+arg_10]
0x1800056ec  lea     rdx, [rdi+1Ch]
0x1800056f0  mov     r8d, 4
0x1800056f6  call    cs:__imp_WdiGetParameterData
0x1800056fc  mov     ebx, eax
0x1800056fe  test    eax, eax
0x180005700  jns     short loc_18000570A
0x180005702  mov     r9d, 221h
0x180005708  jmp     short loc_180005756
0x18000570a  lea     r9, [rbp+arg_10]
0x18000570e  mov     [rbp+arg_10], 0
0x180005716  lea     r8, aResolvererror; "ResolverError"
0x18000571d  xor     edx, edx
0x18000571f  mov     rcx, rsi
0x180005722  call    cs:__imp_WdiGetParameterByName
0x180005728  mov     ebx, eax
0x18000572a  test    eax, eax
0x18000572c  jns     short loc_180005736
0x18000572e  mov     r9d, 22Bh
0x180005734  jmp     short loc_180005756
0x180005736  mov     rcx, [rbp+arg_10]
0x18000573a  lea     rdx, [rdi+20h]
0x18000573e  mov     r8d, 4
0x180005744  call    cs:__imp_WdiGetParameterData
0x18000574a  mov     ebx, eax
0x18000574c  test    eax, eax
0x18000574e  jns     short loc_18000576F
0x180005750  mov     r9d, 231h
0x180005756  mov     [rsp+30h+var_10], eax
0x18000575a  lea     r8, aResolverdataLo; "ResolverData::LoadFromWdi"
0x180005761  xor     ecx, ecx; Level
0x180005763  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x18000576a  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x18000576f  mov     eax, ebx
0x180005771  mov     rbx, [rsp+30h+arg_0]
0x180005776  add     rsp, 30h
0x18000577a  pop     rdi
0x18000577b  pop     rsi
0x18000577c  pop     rbp
0x18000577d  retn
```

# AppendLocalizedDirName

- ea: `0x140078744`
- end: `0x140078b0a`
- name: `AppendLocalizedDirName`
- size: `966`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140078d9c`

## callees

- `0x140002c73`
- `0x140004b70`
- `0x140004c78`
- `0x140004ca8`
- `0x14006a188`
- `0x140078744`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140078857`
- `KERNEL32!FreeLibrary` at `0x140078857`
- `KERNEL32!GetLastError` at `0x14007888f`
- `KERNEL32!GetLastError` at `0x140078964`
- `KERNEL32!GetLastError` at `0x1400789c8`
- `KERNEL32!GetLastError` at `0x140078a50`
- `KERNEL32!GetLastError` at `0x14007888f`
- `KERNEL32!GetLastError` at `0x140078964`
- `KERNEL32!GetLastError` at `0x1400789c8`
- `KERNEL32!GetLastError` at `0x140078a50`
- `KERNEL32!LoadLibraryW` at `0x140078950`
- `KERNEL32!LoadLibraryW` at `0x140078950`
- `KERNEL32!GetProcAddress` at `0x1400789b7`
- `KERNEL32!GetProcAddress` at `0x1400789b7`

## string_xrefs

- `0x140078949`: `Kernel32.dll`
- `0x1400789ad`: `GetFileMUIPath`

## pseudocode

```c
__int64 __fastcall AppendLocalizedDirName(_WORD *a1, unsigned __int16 *a2)
{
  HMODULE v4; // rsi
  int v5; // ebx
  unsigned __int16 *v6; // r8
  int v7; // eax
  unsigned int v8; // edi
  DWORD v9; // ebx
  DWORD LastError; // eax
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  _WORD *v14; // r8
  __int64 v15; // rax
  _WORD *v16; // rcx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  DWORD v19; // eax
  __int64 result; // rax
  __int64 v21; // [rsp+48h] [rbp-460h]
  _BYTE v22[528]; // [rsp+50h] [rbp-458h] BYREF
  unsigned __int16 v23[264]; // [rsp+260h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids);
  }
  memset_0(v22, 0, 0x208u);
  memset_0(v23, 0, 0x208u);
  HIWORD(v21) = 0;
  if ( !LonghornOrMore() )
  {
    v4 = 0;
LABEL_7:
    v5 = 0;
    goto LABEL_8;
  }
  if ( !a1 )
  {
    v8 = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids);
    }
    v9 = 87;
    goto LABEL_55;
  }
  v13 = 260;
  v14 = v22;
  v5 = 1;
  v15 = 2147483646;
  do
  {
    if ( !v15 )
      break;
    if ( !*a1 )
      break;
    *v14++ = *a1++;
    --v15;
    --v13;
  }
  while ( v13 );
  v16 = v14 - 1;
  v8 = v13 == 0 ? 0x8007007A : 0;
  if ( v13 )
    v16 = v14;
  *v16 = 0;
  if ( !v13 )
  {
    v9 = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v8);
    }
    goto LABEL_55;
  }
  LibraryW = LoadLibraryW(L"Kernel32.dll");
  v4 = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_55;
    }
    v12 = 38;
LABEL_38:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, LastError);
    goto LABEL_55;
  }
  ProcAddress = GetProcAddress(LibraryW, "GetFileMUIPath");
  if ( !ProcAddress )
  {
    v19 = GetLastError();
    v9 = v19;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v19);
    }
    goto LABEL_16;
  }
  if ( !((unsigned int (__fastcall *)(__int64, _BYTE *, _QWORD))ProcAddress)(16, v22, 0) )
  {
    v9 = GetLastError();
    if ( v9 != 18 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v8);
      }
      goto LABEL_16;
    }
    goto LABEL_7;
  }
LABEL_8:
  v6 = (unsigned __int16 *)v22;
  if ( v5 )
    v6 = v23;
  v7 = StringCchCopyW(a2, 0x104u, v6);
  v8 = v7;
  if ( v7 < 0
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, (unsigned int)v7);
  }
  v9 = 0;
  if ( v4 )
  {
LABEL_16:
    if ( FreeLibrary(v4)
      || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_55;
    }
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    v12 = 42;
    goto LABEL_38;
  }
LABEL_55:
  result = (unsigned __int16)v8;
  if ( (v8 & 0x80000000) == 0 )
    return v9;
  return result;
}

```

## disassembly

```asm
0x140078744  mov     [rsp+arg_0], rbx
0x140078749  mov     [rsp+arg_10], rbp
0x14007874e  push    rsi
0x14007874f  push    rdi
0x140078750  push    r12
0x140078752  push    r13
0x140078754  push    r14
0x140078756  sub     rsp, 480h
0x14007875d  mov     rax, cs:__security_cookie
0x140078764  xor     rax, rsp
0x140078767  mov     [rsp+4A8h+var_38], rax
0x14007876f  mov     rbp, rdx
0x140078772  mov     rdi, rcx
0x140078775  mov     rcx, cs:WPP_GLOBAL_Control
0x14007877c  lea     r12, WPP_GLOBAL_Control
0x140078783  lea     r13, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids
0x14007878a  cmp     rcx, r12
0x14007878d  jz      short loc_1400787AC
0x14007878f  test    byte ptr [rcx+1Ch], 2
0x140078793  jz      short loc_1400787AC
0x140078795  cmp     byte ptr [rcx+19h], 5
0x140078799  jb      short loc_1400787AC
0x14007879b  mov     rcx, [rcx+10h]
0x14007879f  mov     edx, 23h ; '#'
0x1400787a4  mov     r8, r13
0x1400787a7  call    WPP_SF_
0x1400787ac  mov     ebx, 208h
0x1400787b1  lea     rcx, [rsp+4A8h+var_458]; void *
0x1400787b6  mov     r8d, ebx; Size
0x1400787b9  xor     edx, edx; Val
0x1400787bb  call    memset_0
0x1400787c0  mov     r8d, ebx; Size
0x1400787c3  lea     rcx, [rsp+4A8h+var_248]; void *
0x1400787cb  xor     edx, edx; Val
0x1400787cd  call    memset_0
0x1400787d2  mov     ebx, 104h
0x1400787d7  xor     r14d, r14d
0x1400787da  mov     [rsp+4A8h+var_468], ebx
0x1400787de  mov     [rsp+4A8h+var_460], r14
0x1400787e3  call    LonghornOrMore
0x1400787e8  test    eax, eax
0x1400787ea  jnz     loc_1400788AC
0x1400787f0  mov     esi, r14d
0x1400787f3  mov     ebx, r14d
0x1400787f6  lea     rax, [rsp+4A8h+var_248]
0x1400787fe  test    ebx, ebx
0x140078800  lea     r8, [rsp+4A8h+var_458]
0x140078805  mov     edx, 104h; unsigned __int64
0x14007880a  cmovnz  r8, rax; unsigned __int16 *
0x14007880e  mov     rcx, rbp; unsigned __int16 *
0x140078811  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140078816  mov     edi, eax
0x140078818  test    eax, eax
0x14007881a  jns     short loc_140078848
0x14007881c  mov     rcx, cs:WPP_GLOBAL_Control
0x140078823  cmp     rcx, r12
0x140078826  jz      short loc_140078848
0x140078828  test    byte ptr [rcx+1Ch], 2
0x14007882c  jz      short loc_140078848
0x14007882e  cmp     byte ptr [rcx+19h], 2
0x140078832  jb      short loc_140078848
0x140078834  mov     rcx, [rcx+10h]
0x140078838  mov     edx, 29h ; ')'
0x14007883d  mov     r9d, eax
0x140078840  mov     r8, r13
0x140078843  call    WPP_SF_d
0x140078848  mov     ebx, r14d
0x14007884b  test    rsi, rsi
0x14007884e  jz      loc_140078AD5
0x140078854  mov     rcx, rsi; hLibModule
0x140078857  call    cs:__imp_FreeLibrary
0x14007885e  nop     dword ptr [rax+rax+00h]
0x140078863  test    eax, eax
0x140078865  jnz     loc_140078AD5
0x14007886b  mov     rax, cs:WPP_GLOBAL_Control
0x140078872  cmp     rax, r12
0x140078875  jz      loc_140078AD5
0x14007887b  test    byte ptr [rax+1Ch], 2
0x14007887f  jz      loc_140078AD5
0x140078885  cmp     byte ptr [rax+19h], 3
0x140078889  jb      loc_140078AD5
0x14007888f  call    cs:__imp_GetLastError
0x140078896  nop     dword ptr [rax+rax+00h]
0x14007889b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400788a2  mov     edx, 2Ah ; '*'
0x1400788a7  jmp     loc_140078999
0x1400788ac  test    rdi, rdi
0x1400788af  jz      loc_140078AA4
0x1400788b5  mov     rdx, rbx
0x1400788b8  lea     r8, [rsp+4A8h+var_458]
0x1400788bd  mov     ebx, 1
0x1400788c2  mov     eax, 7FFFFFFEh
0x1400788c7  test    rax, rax
0x1400788ca  jz      short loc_1400788E8
0x1400788cc  movzx   ecx, word ptr [rdi]
0x1400788cf  test    cx, cx
0x1400788d2  jz      short loc_1400788E8
0x1400788d4  mov     [r8], cx
0x1400788d8  add     rdi, 2
0x1400788dc  add     r8, 2
0x1400788e0  sub     rax, rbx
0x1400788e3  sub     rdx, rbx
0x1400788e6  jnz     short loc_1400788C7
0x1400788e8  mov     rax, rdx
0x1400788eb  lea     rcx, [r8-2]
0x1400788ef  neg     rax
0x1400788f2  sbb     edi, edi
0x1400788f4  not     edi
0x1400788f6  and     edi, 8007007Ah
0x1400788fc  test    rdx, rdx
0x1400788ff  cmovnz  rcx, r8
0x140078903  mov     [rcx], r14w
0x140078907  jnz     short loc_140078949
0x140078909  mov     ebx, r14d
0x14007890c  mov     rcx, cs:WPP_GLOBAL_Control
0x140078913  cmp     rcx, r12
0x140078916  jz      loc_140078AD5
0x14007891c  test    byte ptr [rcx+1Ch], 2
0x140078920  jz      loc_140078AD5
0x140078926  cmp     byte ptr [rcx+19h], 2
0x14007892a  jb      loc_140078AD5
0x140078930  mov     rcx, [rcx+10h]
0x140078934  mov     edx, 25h ; '%'
0x140078939  mov     r9d, edi
0x14007893c  mov     r8, r13
0x14007893f  call    WPP_SF_d
0x140078944  jmp     loc_140078AD5
0x140078949  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x140078950  call    cs:__imp_LoadLibraryW
0x140078957  nop     dword ptr [rax+rax+00h]
0x14007895c  mov     rsi, rax
0x14007895f  test    rax, rax
0x140078962  jnz     short loc_1400789AD
0x140078964  call    cs:__imp_GetLastError
0x14007896b  nop     dword ptr [rax+rax+00h]
0x140078970  mov     ebx, eax
0x140078972  mov     rcx, cs:WPP_GLOBAL_Control
0x140078979  cmp     rcx, r12
0x14007897c  jz      loc_140078AD5
0x140078982  test    byte ptr [rcx+1Ch], 2
0x140078986  jz      loc_140078AD5
0x14007898c  cmp     byte ptr [rcx+19h], 3
0x140078990  jb      loc_140078AD5
0x140078996  lea     edx, [rsi+26h]
0x140078999  mov     rcx, [rcx+10h]
0x14007899d  mov     r8, r13
0x1400789a0  mov     r9d, eax
0x1400789a3  call    WPP_SF_d
0x1400789a8  jmp     loc_140078AD5
0x1400789ad  lea     rdx, aGetfilemuipath; "GetFileMUIPath"
0x1400789b4  mov     rcx, rax; hModule
0x1400789b7  call    cs:__imp_GetProcAddress
0x1400789be  nop     dword ptr [rax+rax+00h]
0x1400789c3  test    rax, rax
0x1400789c6  jnz     short loc_140078A13
0x1400789c8  call    cs:__imp_GetLastError
0x1400789cf  nop     dword ptr [rax+rax+00h]
0x1400789d4  mov     ebx, eax
0x1400789d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400789dd  cmp     rcx, r12
0x1400789e0  jz      loc_140078854
0x1400789e6  test    byte ptr [rcx+1Ch], 2
0x1400789ea  jz      loc_140078854
0x1400789f0  cmp     byte ptr [rcx+19h], 3
0x1400789f4  jb      loc_140078854
0x1400789fa  mov     rcx, [rcx+10h]
0x1400789fe  mov     edx, 27h ; '''
0x140078a03  mov     r9d, eax
0x140078a06  mov     r8, r13
0x140078a09  call    WPP_SF_d
0x140078a0e  jmp     loc_140078854
0x140078a13  lea     rcx, [rsp+4A8h+var_460]
0x140078a18  xor     r9d, r9d
0x140078a1b  mov     [rsp+4A8h+var_478], rcx
0x140078a20  lea     rdx, [rsp+4A8h+var_458]
0x140078a25  lea     rcx, [rsp+4A8h+var_468]
0x140078a2a  xor     r8d, r8d
0x140078a2d  mov     [rsp+4A8h+var_480], rcx
0x140078a32  lea     rcx, [rsp+4A8h+var_248]
0x140078a3a  mov     [rsp+4A8h+var_488], rcx
0x140078a3f  lea     ecx, [r9+10h]
0x140078a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140078a48  test    eax, eax
0x140078a4a  jnz     loc_1400787F6
0x140078a50  call    cs:__imp_GetLastError
0x140078a57  nop     dword ptr [rax+rax+00h]
0x140078a5c  mov     ebx, eax
0x140078a5e  cmp     eax, 12h
0x140078a61  jz      loc_1400787F3
0x140078a67  mov     rcx, cs:WPP_GLOBAL_Control
0x140078a6e  cmp     rcx, r12
0x140078a71  jz      loc_140078854
0x140078a77  test    byte ptr [rcx+1Ch], 2
0x140078a7b  jz      loc_140078854
0x140078a81  cmp     byte ptr [rcx+19h], 2
0x140078a85  jb      loc_140078854
0x140078a8b  mov     rcx, [rcx+10h]
0x140078a8f  mov     edx, 28h ; '('
0x140078a94  mov     r9d, edi
0x140078a97  mov     r8, r13
0x140078a9a  call    WPP_SF_d
0x140078a9f  jmp     loc_140078854
0x140078aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140078aab  mov     edi, r14d
0x140078aae  cmp     rcx, r12
0x140078ab1  jz      short loc_140078AD0
0x140078ab3  test    byte ptr [rcx+1Ch], 2
0x140078ab7  jz      short loc_140078AD0
0x140078ab9  cmp     byte ptr [rcx+19h], 2
0x140078abd  jb      short loc_140078AD0
0x140078abf  mov     rcx, [rcx+10h]
0x140078ac3  mov     edx, 24h ; '$'
0x140078ac8  mov     r8, r13
0x140078acb  call    WPP_SF_
0x140078ad0  mov     ebx, 57h ; 'W'
0x140078ad5  test    edi, edi
0x140078ad7  movzx   eax, di
0x140078ada  cmovns  eax, ebx
0x140078add  mov     rcx, [rsp+4A8h+var_38]
0x140078ae5  xor     rcx, rsp; StackCookie
0x140078ae8  call    __security_check_cookie
0x140078aed  lea     r11, [rsp+4A8h+var_28]
0x140078af5  mov     rbx, [r11+30h]
0x140078af9  mov     rbp, [r11+40h]
0x140078afd  mov     rsp, r11
0x140078b00  pop     r14
0x140078b02  pop     r13
0x140078b04  pop     r12
0x140078b06  pop     rdi
0x140078b07  pop     rsi
0x140078b08  retn
```

# CDiscoveryStrategySimpleAsync::StartDiscoverURL(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,IRADCDiscoveryListener *)

- ea: `0x180024260`
- end: `0x180024533`
- name: `?StartDiscoverURL@CDiscoveryStrategySimpleAsync@@UEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVIRADCDiscoveryListener@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18001e974`
- `0x180024260`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024454`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800243e9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800243e9`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x180024339`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x180024339`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CDiscoveryStrategySimpleAsync::StartDiscoverURL(_DWORD *lpParameter, void *a2, __int64 a3)
{
  unsigned int v6; // eax
  signed int v7; // edi
  __int64 v8; // rax
  signed int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  signed int v12; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  signed int v17; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _WORD *v19; // rax

  if ( lpParameter[18] )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)lpParameter + 32LL))(lpParameter);
  if ( *((_QWORD *)lpParameter + 6) || *((_QWORD *)lpParameter + 8) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_7525bbe22447358051ca750e5c7a2ac3_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147023649);
    }
    v7 = -2147023649;
    goto LABEL_38;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_7525bbe22447358051ca750e5c7a2ac3_Traceguids,
        v6,
        -2147024809);
    }
    v7 = -2147024809;
    goto LABEL_38;
  }
  v8 = SHCreateWorkerWindowW(CDiscoveryStrategySimpleAsync::SyncHelperWindowProc, 0, 0, 0, 0, lpParameter);
  *((_QWORD *)lpParameter + 7) = v8;
  if ( v8 )
  {
    std::wstring::operator=(lpParameter + 4, a2);
    *((_QWORD *)lpParameter + 8) = a3;
    Thread = CreateThread(0, 0, CDiscoveryStrategySimpleAsync::ThreadProc, lpParameter, 0, 0);
    *((_QWORD *)lpParameter + 6) = Thread;
    if ( Thread )
    {
      v7 = 0;
      goto LABEL_39;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_7525bbe22447358051ca750e5c7a2ac3_Traceguids, v16, v15);
    }
    v17 = GetLastError();
    v7 = v17;
    if ( v17 > 0 )
      v7 = (unsigned __int16)v17 | 0x80070000;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_7525bbe22447358051ca750e5c7a2ac3_Traceguids, v11, v10);
    }
    v12 = GetLastError();
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
  }
  if ( v7 < 0 )
  {
LABEL_38:
    v19 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(lpParameter + 4);
    *((_QWORD *)lpParameter + 4) = 0;
    *v19 = 0;
    *((_QWORD *)lpParameter + 8) = 0;
  }
LABEL_39:
  std::wstring::~wstring(a2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024260  mov     r11, rsp
0x180024263  push    rdi
0x180024264  push    r14
0x180024266  push    r15
0x180024268  sub     rsp, 60h
0x18002426c  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x180024274  mov     [r11+18h], rbx
0x180024278  mov     [r11+20h], rsi
0x18002427c  mov     rax, cs:__security_cookie
0x180024283  xor     rax, rsp
0x180024286  mov     [rsp+78h+var_20], rax
0x18002428b  mov     rbx, r8
0x18002428e  mov     r15, rdx
0x180024291  mov     r14, rcx
0x180024294  mov     [rsp+78h+var_40], rcx
0x180024299  mov     [r11-30h], rdx
0x18002429d  xor     esi, esi
0x18002429f  cmp     [rcx+48h], esi
0x1800242a2  jz      short loc_1800242B0
0x1800242a4  mov     rax, [rcx]
0x1800242a7  mov     rax, [rax+20h]
0x1800242ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242b0  cmp     [r14+30h], rsi
0x1800242b4  jnz     loc_180024476
0x1800242ba  cmp     [r14+40h], rsi
0x1800242be  jnz     loc_180024476
0x1800242c4  test    rbx, rbx
0x1800242c7  jnz     short loc_180024320
0x1800242c9  lea     rax, WPP_GLOBAL_Control
0x1800242d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242d7  cmp     rcx, rax
0x1800242da  jz      short loc_180024312
0x1800242dc  test    byte ptr [rcx+1Ch], 8
0x1800242e0  jz      short loc_180024312
0x1800242e2  cmp     byte ptr [rcx+19h], 2
0x1800242e6  jb      short loc_180024312
0x1800242e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800242ed  lea     edx, [rbx+0Bh]
0x1800242f0  mov     [rsp+78h+dwCreationFlags], 80070057h
0x1800242f8  mov     r9d, eax
0x1800242fb  lea     r8, WPP_7525bbe22447358051ca750e5c7a2ac3_Traceguids
0x180024302  mov     rcx, cs:WPP_GLOBAL_Control
0x180024309  mov     rcx, [rcx+10h]
0x18002430d  call    WPP_SF_Dd
0x180024312  mov     edi, 80070057h
0x180024317  mov     [rsp+78h+var_48], edi
0x18002431b  jmp     loc_1800244F2
0x180024320  mov     [rsp+78h+lpThreadId], r14
0x180024325  mov     qword ptr [rsp+78h+dwCreationFlags], rsi
0x18002432a  xor     r9d, r9d
0x18002432d  xor     r8d, r8d
0x180024330  xor     edx, edx
0x180024332  lea     rcx, ?SyncHelperWindowProc@CDiscoveryStrategySimpleAsync@@KA_JPEAUHWND__@@I_K_J@Z; CDiscoveryStrategySimpleAsync::SyncHelperWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x180024339  call    cs:__imp_SHCreateWorkerWindowW
0x18002433f  mov     [r14+38h], rax
0x180024343  test    rax, rax
0x180024346  jnz     short loc_1800243C2
0x180024348  lea     rax, WPP_GLOBAL_Control
0x18002434f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024356  cmp     rcx, rax
0x180024359  jz      short loc_1800243A4
0x18002435b  test    byte ptr [rcx+1Ch], 8
0x18002435f  jz      short loc_1800243A4
0x180024361  cmp     byte ptr [rcx+19h], 2
0x180024365  jb      short loc_1800243A4
0x180024367  call    cs:__imp_GetLastError
0x18002436d  mov     ebx, eax
0x18002436f  test    eax, eax
0x180024371  jle     short loc_18002437C
0x180024373  movzx   ebx, ax
0x180024376  or      ebx, 80070000h
0x18002437c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180024381  mov     edx, 0Ch
0x180024386  mov     [rsp+78h+dwCreationFlags], ebx
0x18002438a  mov     r9d, eax
0x18002438d  lea     r8, WPP_7525bbe22447358051ca750e5c7a2ac3_Traceguids
0x180024394  mov     rcx, cs:WPP_GLOBAL_Control
0x18002439b  mov     rcx, [rcx+10h]
0x18002439f  call    WPP_SF_Dd
0x1800243a4  call    cs:__imp_GetLastError
0x1800243aa  mov     edi, eax
0x1800243ac  test    eax, eax
0x1800243ae  jle     short loc_1800243B9
0x1800243b0  movzx   edi, ax
0x1800243b3  or      edi, 80070000h
0x1800243b9  mov     [rsp+78h+var_48], edi
0x1800243bd  jmp     loc_1800244EE
0x1800243c2  lea     rcx, [r14+10h]
0x1800243c6  mov     rdx, r15
0x1800243c9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800243ce  mov     [r14+40h], rbx
0x1800243d2  mov     [rsp+78h+lpThreadId], rsi; lpThreadId
0x1800243d7  mov     [rsp+78h+dwCreationFlags], esi; dwCreationFlags
0x1800243db  mov     r9, r14; lpParameter
0x1800243de  lea     r8, ?ThreadProc@CDiscoveryStrategySimpleAsync@@KAKPEAX@Z; lpStartAddress
0x1800243e5  xor     edx, edx; dwStackSize
0x1800243e7  xor     ecx, ecx; lpThreadAttributes
0x1800243e9  call    cs:__imp_CreateThread
0x1800243ef  mov     [r14+30h], rax
0x1800243f3  test    rax, rax
0x1800243f6  jnz     short loc_18002446F
0x1800243f8  lea     rax, WPP_GLOBAL_Control
0x1800243ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180024406  cmp     rcx, rax
0x180024409  jz      short loc_180024454
0x18002440b  test    byte ptr [rcx+1Ch], 8
0x18002440f  jz      short loc_180024454
0x180024411  cmp     byte ptr [rcx+19h], 2
0x180024415  jb      short loc_180024454
0x180024417  call    cs:__imp_GetLastError
0x18002441d  mov     ebx, eax
0x18002441f  test    eax, eax
0x180024421  jle     short loc_18002442C
0x180024423  movzx   ebx, ax
0x180024426  or      ebx, 80070000h
0x18002442c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180024431  mov     edx, 0Dh
0x180024436  mov     [rsp+78h+dwCreationFlags], ebx
0x18002443a  mov     r9d, eax
0x18002443d  lea     r8, WPP_7525bbe22447358051ca750e5c7a2ac3_Traceguids
0x180024444  mov     rcx, cs:WPP_GLOBAL_Control
0x18002444b  mov     rcx, [rcx+10h]
0x18002444f  call    WPP_SF_Dd
0x180024454  call    cs:__imp_GetLastError
0x18002445a  mov     edi, eax
0x18002445c  test    eax, eax
0x18002445e  jle     short loc_180024469
0x180024460  movzx   edi, ax
0x180024463  or      edi, 80070000h
0x180024469  mov     [rsp+78h+var_48], edi
0x18002446d  jmp     short loc_1800244EE
0x18002446f  mov     edi, esi
0x180024471  jmp     loc_180024506
0x180024476  lea     rax, WPP_GLOBAL_Control
0x18002447d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024484  cmp     rcx, rax
0x180024487  jz      short loc_1800244C1
0x180024489  test    byte ptr [rcx+1Ch], 8
0x18002448d  jz      short loc_1800244C1
0x18002448f  cmp     byte ptr [rcx+19h], 2
0x180024493  jb      short loc_1800244C1
0x180024495  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002449a  mov     edx, 0Ah
0x18002449f  mov     [rsp+78h+dwCreationFlags], 800704DFh
0x1800244a7  mov     r9d, eax
0x1800244aa  lea     r8, WPP_7525bbe22447358051ca750e5c7a2ac3_Traceguids
0x1800244b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244b8  mov     rcx, [rcx+10h]
0x1800244bc  call    WPP_SF_Dd
0x1800244c1  mov     edi, 800704DFh
0x1800244c6  mov     [rsp+78h+var_48], edi
0x1800244ca  jmp     short loc_1800244F2
0x1800244cc  xor     esi, esi
0x1800244ce  mov     edi, [rsp+78h+var_48]
0x1800244d2  mov     r14, [rsp+78h+var_40]
0x1800244d7  mov     r15, [rsp+78h+var_30]
0x1800244dc  jmp     short loc_1800244F2
0x1800244de  xor     esi, esi
0x1800244e0  mov     edi, [rsp+78h+var_48]
0x1800244e4  mov     r14, [rsp+78h+var_40]
0x1800244e9  mov     r15, [rsp+78h+var_30]
0x1800244ee  test    edi, edi
0x1800244f0  jns     short loc_180024506
0x1800244f2  lea     rcx, [r14+10h]
0x1800244f6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800244fb  mov     [r14+20h], rsi
0x1800244ff  mov     [rax], si
0x180024502  mov     [r14+40h], rsi
0x180024506  mov     rcx, r15; void *
0x180024509  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002450e  mov     eax, edi
0x180024510  mov     rcx, [rsp+78h+var_20]
0x180024515  xor     rcx, rsp; StackCookie
0x180024518  call    __security_check_cookie
0x18002451d  lea     r11, [rsp+78h+var_18]
0x180024522  mov     rbx, [r11+30h]
0x180024526  mov     rsi, [r11+38h]
0x18002452a  mov     rsp, r11
0x18002452d  pop     r15
0x18002452f  pop     r14
0x180024531  pop     rdi
0x180024532  retn
```

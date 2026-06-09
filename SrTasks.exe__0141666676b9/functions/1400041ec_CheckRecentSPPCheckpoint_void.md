# _CheckRecentSPPCheckpoint(void)

- ea: `0x1400041ec`
- end: `0x140004407`
- name: `?_CheckRecentSPPCheckpoint@@YAJXZ`
- size: `539`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004a70`

## callees

- `0x140002e1c`
- `0x140002e44`
- `0x1400041ec`
- `0x14000e324`
- `0x14000e41c`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400042f7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400042f7`
- `SRCORE!SrFreeRpPropArray` at `0x1400043aa`
- `SRCORE!SrFreeRpPropArray` at `0x1400043aa`
- `ole32!CoCreateInstance` at `0x140004283`
- `ole32!CoCreateInstance` at `0x140004283`

## pseudocode

```c
__int64 _CheckRecentSPPCheckpoint(void)
{
  __int16 v0; // ax
  int v1; // eax
  HRESULT v2; // ebx
  _QWORD *v3; // r10
  unsigned int v4; // edx
  unsigned __int64 v5; // r8
  __int16 v6; // ax
  unsigned int v7; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-48h] BYREF
  HRESULT v10; // [rsp+38h] [rbp-40h] BYREF
  __int16 v11; // [rsp+3Ch] [rbp-3Ch]
  __int16 v12; // [rsp+3Eh] [rbp-3Ah]
  unsigned int v13; // [rsp+A0h] [rbp+28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp+30h] BYREF
  struct _FILETIME v15; // [rsp+B0h] [rbp+38h]
  __int64 v16; // [rsp+B8h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "_CheckRecentSPPCheckpoint", 0x46u, 1u);
  ppv = 0;
  v13 = 0;
  v16 = 0;
  SystemTimeAsFileTime = 0;
  v10 = CoCreateInstance(&CLSID_SrControl, 0, 1u, &IID_ISrControl, &ppv);
  v0 = 79;
  if ( v10 < 0 )
    goto LABEL_5;
  v11 = 79;
  v1 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v13, &v16);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
        (unsigned int)v1);
    v10 = v2;
    v0 = 86;
LABEL_5:
    v12 = v0;
    goto LABEL_23;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v15 = SystemTimeAsFileTime;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids, v13);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = v13;
  if ( v13 )
  {
    while ( 1 )
    {
      v5 = *(_QWORD *)(152LL * --v4 + v16 + 16);
      if ( *(_QWORD *)&v15 - v5 < 0x58028E44000LL || *(_QWORD *)&v15 < v5 )
        break;
      if ( !v4 )
        goto LABEL_18;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x8000000) != 0 )
      WPP_SF_(v3[2], 13, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
    v10 = 0;
    v6 = 106;
  }
  else
  {
LABEL_18:
    if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x8000000) != 0 )
      WPP_SF_(v3[2], 14, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
    v10 = 1;
    v6 = 111;
  }
  v11 = v6;
LABEL_23:
  SrFreeRpPropArray(v13, &v16);
  v7 = v10;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return v7;
}

```

## disassembly

```asm
0x1400041ec  push    rbp
0x1400041ee  push    rbx
0x1400041ef  push    rsi
0x1400041f0  push    r14
0x1400041f2  mov     rbp, rsp
0x1400041f5  sub     rsp, 78h
0x1400041f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140004200  lea     rsi, WPP_GLOBAL_Control
0x140004207  lea     r14, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x14000420e  cmp     rcx, rsi
0x140004211  jz      short loc_14000422D
0x140004213  test    dword ptr [rcx+1Ch], 20000000h
0x14000421a  jz      short loc_14000422D
0x14000421c  mov     rcx, [rcx+10h]
0x140004220  mov     edx, 0Ah
0x140004225  mov     r8, r14
0x140004228  call    WPP_SF_
0x14000422d  mov     r9d, 1; unsigned __int16
0x140004233  lea     rdx, aCheckrecentspp; "_CheckRecentSPPCheckpoint"
0x14000423a  lea     rcx, [rbp+var_40]; this
0x14000423e  lea     r8d, [r9+45h]; unsigned __int16
0x140004242  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140004247  xor     edx, edx; pUnkOuter
0x140004249  mov     [rbp+var_48], 0
0x140004251  lea     rax, [rbp+var_48]
0x140004255  mov     [rbp+arg_0], 0
0x14000425c  lea     r9, IID_ISrControl; riid
0x140004263  mov     [rbp+arg_18], 0
0x14000426b  lea     rcx, CLSID_SrControl; rclsid
0x140004272  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14000427a  lea     r8d, [rdx+1]; dwClsContext
0x14000427e  mov     [rsp+78h+ppv], rax; ppv
0x140004283  call    cs:__imp_CoCreateInstance
0x140004289  mov     [rbp+var_40], eax
0x14000428c  test    eax, eax
0x14000428e  mov     eax, 4Fh ; 'O'
0x140004293  jns     short loc_14000429E
0x140004295  mov     [rbp+var_3A], ax
0x140004299  jmp     loc_1400043A3
0x14000429e  mov     rcx, [rbp+var_48]
0x1400042a2  lea     r8, [rbp+arg_18]
0x1400042a6  mov     [rbp+var_3C], ax
0x1400042aa  lea     rdx, [rbp+arg_0]
0x1400042ae  mov     rax, [rcx]
0x1400042b1  mov     rax, [rax+18h]
0x1400042b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042ba  mov     ebx, eax
0x1400042bc  test    eax, eax
0x1400042be  jns     short loc_1400042F3
0x1400042c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042c7  cmp     rcx, rsi
0x1400042ca  jz      short loc_1400042E9
0x1400042cc  test    dword ptr [rcx+1Ch], 2000000h
0x1400042d3  jz      short loc_1400042E9
0x1400042d5  mov     rcx, [rcx+10h]
0x1400042d9  mov     edx, 0Bh
0x1400042de  mov     r9d, eax
0x1400042e1  mov     r8, r14
0x1400042e4  call    WPP_SF_d
0x1400042e9  mov     [rbp+var_40], ebx
0x1400042ec  mov     eax, 56h ; 'V'
0x1400042f1  jmp     short loc_140004295
0x1400042f3  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400042f7  call    cs:__imp_GetSystemTimeAsFileTime
0x1400042fd  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x140004300  mov     dword ptr [rbp+arg_10+4], eax
0x140004303  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140004306  mov     dword ptr [rbp+arg_10], eax
0x140004309  mov     r10, cs:WPP_GLOBAL_Control
0x140004310  mov     ebx, 8000000h
0x140004315  cmp     r10, rsi
0x140004318  jz      short loc_14000433C
0x14000431a  test    [r10+1Ch], ebx
0x14000431e  jz      short loc_14000433C
0x140004320  mov     r9d, [rbp+arg_0]
0x140004324  mov     edx, 0Ch
0x140004329  mov     rcx, [r10+10h]
0x14000432d  mov     r8, r14
0x140004330  call    WPP_SF_d
0x140004335  mov     r10, cs:WPP_GLOBAL_Control
0x14000433c  mov     edx, [rbp+arg_0]
0x14000433f  test    edx, edx
0x140004341  jz      short loc_140004377
0x140004343  mov     r9, [rbp+arg_18]
0x140004347  dec     edx
0x140004349  mov     eax, edx
0x14000434b  imul    rcx, rax, 98h
0x140004352  mov     rax, [rbp+arg_10]
0x140004356  mov     r8, [rcx+r9+10h]
0x14000435b  mov     rcx, 58028E44000h
0x140004365  sub     rax, r8
0x140004368  cmp     rax, rcx
0x14000436b  jb      short loc_1400043DD
0x14000436d  cmp     [rbp+arg_10], r8
0x140004371  jb      short loc_1400043DD
0x140004373  test    edx, edx
0x140004375  jnz     short loc_140004347
0x140004377  cmp     r10, rsi
0x14000437a  jz      short loc_140004393
0x14000437c  test    [r10+1Ch], ebx
0x140004380  jz      short loc_140004393
0x140004382  mov     rcx, [r10+10h]
0x140004386  mov     edx, 0Eh
0x14000438b  mov     r8, r14
0x14000438e  call    WPP_SF_
0x140004393  mov     [rbp+var_40], 1
0x14000439a  mov     eax, 6Fh ; 'o'
0x14000439f  mov     [rbp+var_3C], ax
0x1400043a3  mov     ecx, [rbp+arg_0]
0x1400043a6  lea     rdx, [rbp+arg_18]
0x1400043aa  call    cs:__imp_SrFreeRpPropArray
0x1400043b0  mov     rcx, [rbp+var_48]
0x1400043b4  mov     ebx, [rbp+var_40]
0x1400043b7  test    rcx, rcx
0x1400043ba  jz      short loc_1400043C8
0x1400043bc  mov     rdx, [rcx]
0x1400043bf  mov     rax, [rdx+10h]
0x1400043c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043c8  lea     rcx, [rbp+var_40]; this
0x1400043cc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1400043d1  mov     eax, ebx
0x1400043d3  add     rsp, 78h
0x1400043d7  pop     r14
0x1400043d9  pop     rsi
0x1400043da  pop     rbx
0x1400043db  pop     rbp
0x1400043dc  retn
0x1400043dd  cmp     r10, rsi
0x1400043e0  jz      short loc_1400043F9
0x1400043e2  test    [r10+1Ch], ebx
0x1400043e6  jz      short loc_1400043F9
0x1400043e8  mov     rcx, [r10+10h]
0x1400043ec  mov     edx, 0Dh
0x1400043f1  mov     r8, r14
0x1400043f4  call    WPP_SF_
0x1400043f9  mov     [rbp+var_40], 0
0x140004400  mov     eax, 6Ah ; 'j'
0x140004405  jmp     short loc_14000439F
```

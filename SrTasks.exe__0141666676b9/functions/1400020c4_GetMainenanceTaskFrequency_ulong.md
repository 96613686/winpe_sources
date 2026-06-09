# GetMainenanceTaskFrequency(ulong *)

- ea: `0x1400020c4`
- end: `0x1400022b7`
- name: `?GetMainenanceTaskFrequency@@YAJPEAK@Z`
- size: `499`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140002ae8`

## callees

- `0x1400020c4`
- `0x140002e1c`
- `0x140002e44`
- `0x140005ac0`
- `0x140005c10`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400021b8`
- `ADVAPI32!RegOpenKeyExW` at `0x1400021b8`
- `ADVAPI32!RegCloseKey` at `0x14000218a`
- `ADVAPI32!RegCloseKey` at `0x14000227a`
- `ADVAPI32!RegCloseKey` at `0x140002293`
- `ADVAPI32!RegCloseKey` at `0x14000218a`
- `ADVAPI32!RegCloseKey` at `0x14000227a`
- `ADVAPI32!RegCloseKey` at `0x140002293`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000216a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000216a`

## string_xrefs

- `0x1400021ea`: `LastMainenanceTaskRunTimeStamp`
- `0x14000210c`: `GetMainenanceTaskFrequency`

## pseudocode

```c
__int64 __fastcall GetMainenanceTaskFrequency(unsigned int *a1)
{
  signed int v2; // ebx
  LSTATUS v3; // eax
  int v4; // r9d
  __int16 v5; // ax
  unsigned int v6; // esi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rax
  HKEY v9; // rcx
  int v11; // [rsp+30h] [rbp-40h] BYREF
  __int16 v12; // [rsp+34h] [rbp-3Ch]
  __int16 v13; // [rsp+36h] [rbp-3Ah]
  HKEY hKey; // [rsp+A0h] [rbp+30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp+38h] BYREF
  unsigned __int64 v16; // [rsp+B0h] [rbp+40h]
  unsigned __int64 v17; // [rsp+B8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "GetMainenanceTaskFrequency", 0x16Fu, 1u);
  hKey = 0;
  SystemTimeAsFileTime = 0;
  v17 = 0;
  if ( a1 )
  {
    v11 = 0;
    v12 = 375;
    *a1 = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v16 = (unsigned __int64)SystemTimeAsFileTime;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore",
           0,
           0x2001Fu,
           &hKey);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    v11 = v2;
    v5 = 382;
    if ( v2 < 0 )
      goto LABEL_11;
    v12 = 382;
    v6 = 0;
    if ( !(unsigned int)SxRegReadULONGLONG(hKey, L"LastMainenanceTaskRunTimeStamp", &v17, v4) )
    {
      v8 = (v16 - v17) / 0xC92A69C000LL;
      v7 = (v16 - v17) % 0xC92A69C000LL;
      v6 = v8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_cc2da48973373651002ff2feee037f2e_Traceguids,
          (unsigned int)v8);
      }
    }
    v2 = SxRegWriteULONGLONG(hKey, (const unsigned __int16 *)v7, v16);
    v11 = v2;
    v5 = 393;
    if ( v2 < 0 )
    {
LABEL_11:
      v13 = v5;
    }
    else
    {
      v12 = 393;
      *a1 = v6;
    }
    v9 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      v2 = v11;
      v9 = 0;
      hKey = 0;
    }
    if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v9);
      hKey = 0;
    }
  }
  else
  {
    v2 = -2147024809;
    v13 = 375;
    v11 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400020c4  push    rbp
0x1400020c6  push    rbx
0x1400020c7  push    rsi
0x1400020c8  push    rdi
0x1400020c9  push    r15
0x1400020cb  mov     rbp, rsp
0x1400020ce  sub     rsp, 70h
0x1400020d2  mov     rdi, rcx
0x1400020d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020dc  lea     r15, WPP_GLOBAL_Control
0x1400020e3  cmp     rcx, r15
0x1400020e6  jz      short loc_140002106
0x1400020e8  test    dword ptr [rcx+1Ch], 20000000h
0x1400020ef  jz      short loc_140002106
0x1400020f1  mov     rcx, [rcx+10h]
0x1400020f5  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x1400020fc  mov     edx, 1Ah
0x140002101  call    WPP_SF_
0x140002106  mov     r9d, 1; unsigned __int16
0x14000210c  lea     rdx, aGetmainenancet; "GetMainenanceTaskFrequency"
0x140002113  mov     r8d, 16Fh; unsigned __int16
0x140002119  lea     rcx, [rbp+var_40]; this
0x14000211d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140002122  mov     [rbp+hKey], 0
0x14000212a  mov     eax, 177h
0x14000212f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x140002137  mov     [rbp+arg_18], 0
0x14000213f  test    rdi, rdi
0x140002142  jnz     short loc_140002155
0x140002144  mov     ebx, 80070057h
0x140002149  mov     [rbp+var_3A], ax
0x14000214d  mov     [rbp+var_40], ebx
0x140002150  jmp     loc_1400022A1
0x140002155  mov     [rbp+var_40], 0
0x14000215c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002160  mov     [rbp+var_3C], ax
0x140002164  mov     dword ptr [rdi], 0
0x14000216a  call    cs:__imp_GetSystemTimeAsFileTime
0x140002170  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x140002173  mov     rcx, [rbp+hKey]; hKey
0x140002177  mov     dword ptr [rbp+arg_10+4], eax
0x14000217a  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000217d  mov     dword ptr [rbp+arg_10], eax
0x140002180  lea     rax, [rcx-1]
0x140002184  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002188  ja      short loc_140002198
0x14000218a  call    cs:__imp_RegCloseKey
0x140002190  mov     [rbp+hKey], 0
0x140002198  lea     rax, [rbp+hKey]
0x14000219c  mov     r9d, 2001Fh; samDesired
0x1400021a2  xor     r8d, r8d; ulOptions
0x1400021a5  mov     [rsp+70h+phkResult], rax; phkResult
0x1400021aa  lea     rdx, s_cszSRRegKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400021b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400021b8  call    cs:__imp_RegOpenKeyExW
0x1400021be  mov     ebx, eax
0x1400021c0  test    eax, eax
0x1400021c2  jle     short loc_1400021CD
0x1400021c4  movzx   ebx, ax
0x1400021c7  or      ebx, 80070000h
0x1400021cd  mov     [rbp+var_40], ebx
0x1400021d0  mov     eax, 17Eh
0x1400021d5  test    ebx, ebx
0x1400021d7  jns     short loc_1400021E2
0x1400021d9  mov     [rbp+var_3A], ax
0x1400021dd  jmp     loc_14000226C
0x1400021e2  mov     rcx, [rbp+hKey]; hKey
0x1400021e6  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x1400021ea  lea     rdx, c_wszSRLastMainenanceTaskRun; "LastMainenanceTaskRunTimeStamp"
0x1400021f1  mov     [rbp+var_3C], ax
0x1400021f5  xor     esi, esi
0x1400021f7  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x1400021fc  test    eax, eax
0x1400021fe  jnz     short loc_140002247
0x140002200  mov     rax, [rbp+arg_10]
0x140002204  xor     edx, edx
0x140002206  sub     rax, [rbp+arg_18]
0x14000220a  mov     rcx, 0C92A69C000h
0x140002214  div     rcx
0x140002217  mov     rsi, rax
0x14000221a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002221  cmp     rcx, r15
0x140002224  jz      short loc_140002247
0x140002226  test    dword ptr [rcx+1Ch], 8000000h
0x14000222d  jz      short loc_140002247
0x14000222f  mov     rcx, [rcx+10h]
0x140002233  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x14000223a  mov     edx, 1Bh
0x14000223f  mov     r9d, eax
0x140002242  call    WPP_SF_d
0x140002247  mov     r8, [rbp+arg_10]; unsigned __int64
0x14000224b  mov     rcx, [rbp+hKey]; hKey
0x14000224f  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x140002254  mov     ebx, eax
0x140002256  mov     [rbp+var_40], eax
0x140002259  test    eax, eax
0x14000225b  mov     eax, 189h
0x140002260  js      loc_1400021D9
0x140002266  mov     [rbp+var_3C], ax
0x14000226a  mov     [rdi], esi
0x14000226c  mov     rcx, [rbp+hKey]; hKey
0x140002270  lea     rax, [rcx-1]
0x140002274  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002278  ja      short loc_140002289
0x14000227a  call    cs:__imp_RegCloseKey
0x140002280  mov     ebx, [rbp+var_40]
0x140002283  xor     ecx, ecx; hKey
0x140002285  mov     [rbp+hKey], rcx
0x140002289  lea     rdx, [rcx-1]
0x14000228d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140002291  ja      short loc_1400022A1
0x140002293  call    cs:__imp_RegCloseKey
0x140002299  mov     [rbp+hKey], 0
0x1400022a1  lea     rcx, [rbp+var_40]; this
0x1400022a5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1400022aa  mov     eax, ebx
0x1400022ac  add     rsp, 70h
0x1400022b0  pop     r15
0x1400022b2  pop     rdi
0x1400022b3  pop     rsi
0x1400022b4  pop     rbx
0x1400022b5  pop     rbp
0x1400022b6  retn
```

# SxQueryGroupPolicy(ushort const *,ushort const *,int *)

- ea: `0x140005784`
- end: `0x140005954`
- name: `?SxQueryGroupPolicy@@YAJPEBG0PEAH@Z`
- size: `464`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001b3c`

## callees

- `0x140005784`
- `0x14000595c`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400057fe`
- `ADVAPI32!RegOpenKeyExW` at `0x1400058ac`
- `ADVAPI32!RegOpenKeyExW` at `0x1400057fe`
- `ADVAPI32!RegOpenKeyExW` at `0x1400058ac`
- `ADVAPI32!RegCloseKey` at `0x140005868`
- `ADVAPI32!RegCloseKey` at `0x14000587e`
- `ADVAPI32!RegCloseKey` at `0x140005929`
- `ADVAPI32!RegCloseKey` at `0x140005868`
- `ADVAPI32!RegCloseKey` at `0x14000587e`
- `ADVAPI32!RegCloseKey` at `0x140005929`

## pseudocode

```c
__int64 __fastcall SxQueryGroupPolicy(unsigned __int16 *a1, const unsigned __int16 *a2, int *a3)
{
  int DWORD; // ebx
  __int16 v5; // ax
  __int16 v6; // ax
  HKEY v7; // rcx
  int v8; // eax
  int v10; // [rsp+30h] [rbp-40h] BYREF
  int v11; // [rsp+34h] [rbp-3Ch]
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF
  const unsigned __int16 *v13; // [rsp+88h] [rbp+18h] BYREF

  v13 = a2;
  hKey = (HKEY)a1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "SxQueryGroupPolicy", 0x400u, 2u);
  hKey = 0;
  LODWORD(v13) = 0;
  if ( !a3 )
  {
    v11 = 67765257;
    DWORD = -2147024809;
    goto LABEL_21;
  }
  *a3 = 0;
  LOWORD(v11) = 1034;
  v10 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\SystemRestore",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_9;
  }
  DWORD = SxRegReadDWORD(hKey, L"DisableSR", (unsigned int *)&v13, 1);
  v10 = DWORD;
  v5 = 1042;
  if ( DWORD < 0 )
  {
LABEL_4:
    HIWORD(v11) = v5;
    goto LABEL_22;
  }
  LOWORD(v11) = 1042;
  if ( DWORD )
  {
LABEL_9:
    v7 = hKey;
    if ( hKey )
    {
      if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        RegCloseKey(hKey);
        v7 = 0;
        hKey = 0;
      }
      if ( (unsigned __int64)v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(v7);
        hKey = 0;
      }
    }
    if ( RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Policies\\Microsoft\\Windows NT\\SystemRestore",
           0,
           0x20019u,
           &hKey) )
    {
      goto LABEL_19;
    }
    v8 = SxRegReadDWORD(hKey, L"DisableSR", (unsigned int *)&v13, 1);
    v10 = v8;
    DWORD = v8;
    if ( v8 < 0 )
    {
      v5 = 1057;
      goto LABEL_4;
    }
    if ( v8 )
    {
LABEL_19:
      *a3 = 0;
      DWORD = 1;
      v6 = 1069;
      goto LABEL_8;
    }
    *a3 = (_DWORD)v13 != 0;
    v6 = 1061;
  }
  else
  {
    *a3 = (_DWORD)v13 != 0;
    v6 = 1046;
  }
  DWORD = 0;
LABEL_8:
  LOWORD(v11) = v6;
LABEL_21:
  v10 = DWORD;
LABEL_22:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return (unsigned int)DWORD;
}

```

## disassembly

```asm
0x140005784  mov     rax, rsp
0x140005787  mov     [rax+18h], rbx
0x14000578b  mov     [rax+20h], rdi
0x14000578f  mov     [rax+10h], rdx
0x140005793  mov     [rax+8], rcx
0x140005797  push    rbp
0x140005798  mov     rbp, rsp
0x14000579b  sub     rsp, 70h
0x14000579f  mov     rdi, r8
0x1400057a2  lea     rdx, aSxquerygrouppo; "SxQueryGroupPolicy"
0x1400057a9  mov     r8d, 400h; unsigned __int16
0x1400057af  lea     rcx, [rbp+var_40]; this
0x1400057b3  mov     r9d, 2; unsigned __int16
0x1400057b9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1400057be  xor     ecx, ecx
0x1400057c0  mov     [rbp+hKey], rcx
0x1400057c4  mov     dword ptr [rbp+arg_8], ecx
0x1400057c7  test    rdi, rdi
0x1400057ca  jz      loc_14000590C
0x1400057d0  mov     eax, 40Ah
0x1400057d5  mov     [rdi], ecx
0x1400057d7  mov     word ptr [rbp+var_3C], ax
0x1400057db  lea     rdx, s_cszGroupPolicy; "Software\\Policies\\Microsoft\\Windows "...
0x1400057e2  lea     rax, [rbp+hKey]
0x1400057e6  mov     [rbp+var_40], ecx
0x1400057e9  mov     r9d, 20019h; samDesired
0x1400057ef  mov     [rsp+70h+phkResult], rax; phkResult
0x1400057f4  xor     r8d, r8d; ulOptions
0x1400057f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400057fe  call    cs:__imp_RegOpenKeyExW
0x140005804  test    eax, eax
0x140005806  jnz     short loc_140005859
0x140005808  mov     rcx, [rbp+hKey]; hKey
0x14000580c  lea     r9d, [rax+1]; int
0x140005810  lea     r8, [rbp+arg_8]; unsigned int *
0x140005814  lea     rdx, s_cszDisableSR; "DisableSR"
0x14000581b  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x140005820  mov     ebx, eax
0x140005822  mov     [rbp+var_40], eax
0x140005825  test    eax, eax
0x140005827  mov     eax, 412h
0x14000582c  jns     short loc_140005837
0x14000582e  mov     word ptr [rbp+var_3C+2], ax
0x140005832  jmp     loc_14000591B
0x140005837  mov     word ptr [rbp+var_3C], ax
0x14000583b  test    ebx, ebx
0x14000583d  jnz     short loc_140005859
0x14000583f  xor     eax, eax
0x140005841  cmp     dword ptr [rbp+arg_8], eax
0x140005844  setnz   al
0x140005847  mov     [rdi], eax
0x140005849  mov     eax, 416h
0x14000584e  xor     ebx, ebx
0x140005850  mov     word ptr [rbp+var_3C], ax
0x140005854  jmp     loc_140005918
0x140005859  mov     rcx, [rbp+hKey]; hKey
0x14000585d  test    rcx, rcx
0x140005860  jz      short loc_14000588C
0x140005862  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140005866  jz      short loc_140005874
0x140005868  call    cs:__imp_RegCloseKey
0x14000586e  xor     ecx, ecx; hKey
0x140005870  mov     [rbp+hKey], rcx
0x140005874  lea     rax, [rcx-1]
0x140005878  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000587c  ja      short loc_14000588C
0x14000587e  call    cs:__imp_RegCloseKey
0x140005884  mov     [rbp+hKey], 0
0x14000588c  lea     rax, [rbp+hKey]
0x140005890  mov     r9d, 20019h; samDesired
0x140005896  xor     r8d, r8d; ulOptions
0x140005899  mov     [rsp+70h+phkResult], rax; phkResult
0x14000589e  lea     rdx, s_cszGroupPolicy; "Software\\Policies\\Microsoft\\Windows "...
0x1400058a5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400058ac  call    cs:__imp_RegOpenKeyExW
0x1400058b2  test    eax, eax
0x1400058b4  jnz     short loc_1400058F7
0x1400058b6  mov     rcx, [rbp+hKey]; hKey
0x1400058ba  lea     r9d, [rax+1]; int
0x1400058be  lea     r8, [rbp+arg_8]; unsigned int *
0x1400058c2  lea     rdx, s_cszDisableSR; "DisableSR"
0x1400058c9  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1400058ce  mov     [rbp+var_40], eax
0x1400058d1  mov     ebx, eax
0x1400058d3  test    eax, eax
0x1400058d5  jns     short loc_1400058E1
0x1400058d7  mov     eax, 421h
0x1400058dc  jmp     loc_14000582E
0x1400058e1  jnz     short loc_1400058F7
0x1400058e3  xor     eax, eax
0x1400058e5  cmp     dword ptr [rbp+arg_8], eax
0x1400058e8  setnz   al
0x1400058eb  mov     [rdi], eax
0x1400058ed  mov     eax, 425h
0x1400058f2  jmp     loc_14000584E
0x1400058f7  mov     dword ptr [rdi], 0
0x1400058fd  mov     ebx, 1
0x140005902  mov     eax, 42Dh
0x140005907  jmp     loc_140005850
0x14000590c  mov     [rbp+var_3C], 40A0409h
0x140005913  mov     ebx, 80070057h
0x140005918  mov     [rbp+var_40], ebx
0x14000591b  mov     rcx, [rbp+hKey]; hKey
0x14000591f  lea     rdx, [rcx-1]
0x140005923  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140005927  ja      short loc_140005937
0x140005929  call    cs:__imp_RegCloseKey
0x14000592f  mov     [rbp+hKey], 0
0x140005937  lea     rcx, [rbp+var_40]; this
0x14000593b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140005940  lea     r11, [rsp+70h+var_s0]
0x140005945  mov     eax, ebx
0x140005947  mov     rbx, [r11+20h]
0x14000594b  mov     rdi, [r11+28h]
0x14000594f  mov     rsp, r11
0x140005952  pop     rbp
0x140005953  retn
```

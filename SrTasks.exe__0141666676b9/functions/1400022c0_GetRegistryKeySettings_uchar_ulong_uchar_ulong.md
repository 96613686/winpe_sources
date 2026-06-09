# GetRegistryKeySettings(uchar *,ulong *,uchar *,ulong *)

- ea: `0x1400022c0`
- end: `0x14000247c`
- name: `?GetRegistryKeySettings@@YAJPEAEPEAK01@Z`
- size: `444`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002ae8`

## callees

- `0x1400022c0`
- `0x140002e1c`
- `0x14000595c`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400023b0`
- `ADVAPI32!RegOpenKeyExW` at `0x1400023b0`
- `ADVAPI32!RegCloseKey` at `0x14000243a`
- `ADVAPI32!RegCloseKey` at `0x140002453`
- `ADVAPI32!RegCloseKey` at `0x14000243a`
- `ADVAPI32!RegCloseKey` at `0x140002453`

## string_xrefs

- `0x140002318`: `GetRegistryKeySettings`

## pseudocode

```c
__int64 __fastcall GetRegistryKeySettings(bool *a1, unsigned int *a2, bool *a3, unsigned int *a4)
{
  __int16 v8; // ax
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  HKEY v13; // rcx
  unsigned int v15; // [rsp+30h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-21h] BYREF
  int v17; // [rsp+40h] [rbp-19h] BYREF
  __int16 v18; // [rsp+44h] [rbp-15h]
  __int16 v19; // [rsp+46h] [rbp-13h]
  unsigned int v20; // [rsp+C0h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "GetRegistryKeySettings", 0x19Fu, 1u);
  v8 = 423;
  hKey = 0;
  v20 = 0;
  v15 = 0;
  if ( a1 && (v18 = 423, v8 = 424, a2) && (v18 = 424, v8 = 425, a3) && (v18 = 425, v8 = 426, a4) )
  {
    v17 = 0;
    v18 = 426;
    *a1 = 0;
    *a2 = 0;
    *a3 = 0;
    *a4 = 0;
    v10 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore",
            0,
            0x20019u,
            &hKey);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v17 = v10;
    if ( v10 >= 0 )
    {
      v18 = 432;
      v11 = SxRegReadDWORD(hKey, L"ScopeSnapshots", &v20, 1);
      v12 = SxRegReadDWORD(hKey, L"SystemRestorePointTimeToLive", &v15, 1);
      *a1 = v11 == 0;
      *a3 = v12 == 0;
      if ( !v11 )
        *a2 = v20;
      *a4 = v15;
    }
    else
    {
      v19 = 432;
    }
    v13 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      v13 = 0;
      hKey = 0;
    }
    v9 = v17;
    if ( (unsigned __int64)v13 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v13);
      hKey = 0;
    }
  }
  else
  {
    v9 = -2147024809;
    v19 = v8;
    v17 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return v9;
}

```

## disassembly

```asm
0x1400022c0  push    rbp
0x1400022c2  push    rbx
0x1400022c3  push    rsi
0x1400022c4  push    rdi
0x1400022c5  push    r14
0x1400022c7  push    r15
0x1400022c9  lea     rbp, [rsp-2Fh]
0x1400022ce  sub     rsp, 88h
0x1400022d5  mov     rdi, r9
0x1400022d8  mov     r14, r8
0x1400022db  mov     rsi, rdx
0x1400022de  mov     r15, rcx
0x1400022e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022e8  lea     rax, WPP_GLOBAL_Control
0x1400022ef  cmp     rcx, rax
0x1400022f2  jz      short loc_140002312
0x1400022f4  test    dword ptr [rcx+1Ch], 20000000h
0x1400022fb  jz      short loc_140002312
0x1400022fd  mov     rcx, [rcx+10h]
0x140002301  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x140002308  mov     edx, 1Ch
0x14000230d  call    WPP_SF_
0x140002312  mov     r9d, 1; unsigned __int16
0x140002318  lea     rdx, aGetregistrykey; "GetRegistryKeySettings"
0x14000231f  mov     r8d, 19Fh; unsigned __int16
0x140002325  lea     rcx, [rbp+57h+var_70]; this
0x140002329  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000232e  xor     ecx, ecx
0x140002330  mov     eax, 1A7h
0x140002335  mov     [rbp+57h+hKey], rcx
0x140002339  mov     [rbp+57h+arg_0], ecx
0x14000233c  mov     [rbp+57h+var_80], ecx
0x14000233f  test    r15, r15
0x140002342  jnz     short loc_140002355
0x140002344  mov     ebx, 80070057h
0x140002349  mov     [rbp+57h+var_6A], ax
0x14000234d  mov     [rbp+57h+var_70], ebx
0x140002350  jmp     loc_140002461
0x140002355  mov     [rbp+57h+var_6C], ax
0x140002359  mov     eax, 1A8h
0x14000235e  test    rsi, rsi
0x140002361  jz      short loc_140002344
0x140002363  mov     [rbp+57h+var_6C], ax
0x140002367  mov     eax, 1A9h
0x14000236c  test    r14, r14
0x14000236f  jz      short loc_140002344
0x140002371  mov     [rbp+57h+var_6C], ax
0x140002375  mov     eax, 1AAh
0x14000237a  test    rdi, rdi
0x14000237d  jz      short loc_140002344
0x14000237f  mov     [rbp+57h+var_70], ecx
0x140002382  lea     rdx, s_cszSRRegKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x140002389  mov     [rbp+57h+var_6C], ax
0x14000238d  mov     r9d, 20019h; samDesired
0x140002393  mov     [r15], cl
0x140002396  lea     rax, [rbp+57h+hKey]
0x14000239a  mov     [rsi], ecx
0x14000239c  xor     r8d, r8d; ulOptions
0x14000239f  mov     [r14], cl
0x1400023a2  mov     [rdi], ecx
0x1400023a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400023ab  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1400023b0  call    cs:__imp_RegOpenKeyExW
0x1400023b6  test    eax, eax
0x1400023b8  jle     short loc_1400023C2
0x1400023ba  movzx   eax, ax
0x1400023bd  or      eax, 80070000h
0x1400023c2  mov     [rbp+57h+var_70], eax
0x1400023c5  test    eax, eax
0x1400023c7  mov     eax, 1B0h
0x1400023cc  jns     short loc_1400023D4
0x1400023ce  mov     [rbp+57h+var_6A], ax
0x1400023d2  jmp     short loc_14000242C
0x1400023d4  mov     rcx, [rbp+57h+hKey]; hKey
0x1400023d8  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x1400023dc  mov     r9d, 1; int
0x1400023e2  mov     [rbp+57h+var_6C], ax
0x1400023e6  lea     rdx, c_wszScopeSnapshots; "ScopeSnapshots"
0x1400023ed  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1400023f2  mov     rcx, [rbp+57h+hKey]; hKey
0x1400023f6  lea     r8, [rbp+57h+var_80]; unsigned int *
0x1400023fa  mov     r9d, 1; int
0x140002400  lea     rdx, c_wszRestorePointTimeToLive; "SystemRestorePointTimeToLive"
0x140002407  mov     ebx, eax
0x140002409  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x14000240e  test    eax, eax
0x140002410  setz    cl
0x140002413  test    ebx, ebx
0x140002415  setz    al
0x140002418  mov     [r15], al
0x14000241b  mov     [r14], cl
0x14000241e  test    ebx, ebx
0x140002420  jnz     short loc_140002427
0x140002422  mov     eax, [rbp+57h+arg_0]
0x140002425  mov     [rsi], eax
0x140002427  mov     eax, [rbp+57h+var_80]
0x14000242a  mov     [rdi], eax
0x14000242c  mov     rcx, [rbp+57h+hKey]; hKey
0x140002430  lea     rax, [rcx-1]
0x140002434  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002438  ja      short loc_140002446
0x14000243a  call    cs:__imp_RegCloseKey
0x140002440  xor     ecx, ecx; hKey
0x140002442  mov     [rbp+57h+hKey], rcx
0x140002446  mov     ebx, [rbp+57h+var_70]
0x140002449  lea     rdx, [rcx-1]
0x14000244d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140002451  ja      short loc_140002461
0x140002453  call    cs:__imp_RegCloseKey
0x140002459  mov     [rbp+57h+hKey], 0
0x140002461  lea     rcx, [rbp+57h+var_70]; this
0x140002465  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000246a  mov     eax, ebx
0x14000246c  add     rsp, 88h
0x140002473  pop     r15
0x140002475  pop     r14
0x140002477  pop     rdi
0x140002478  pop     rsi
0x140002479  pop     rbx
0x14000247a  pop     rbp
0x14000247b  retn
```

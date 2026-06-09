# DEBUGMSGBOX(ushort const *,...)

- ea: `0x1400036d8`
- end: `0x140003912`
- name: `?DEBUGMSGBOX@@YAHPEBGZZ`
- size: `570`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `44`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001cb8`
- `0x140001e2c`
- `0x140002140`
- `0x140002300`
- `0x1400024d4`
- `0x140002838`
- `0x140002c94`
- `0x14000300c`
- `0x140003150`
- `0x140003218`
- `0x1400036d8`
- `0x140003948`
- `0x140004288`
- `0x14000445c`
- `0x140004760`
- `0x140005988`
- `0x140005bc0`
- `0x1400063e0`
- `0x140006544`
- `0x14000660c`
- `0x1400066f4`
- `0x1400068bc`
- `0x140006a88`
- `0x140006e24`
- `0x140007158`
- `0x1400076e0`
- `0x140007bf8`
- `0x140007d88`
- `0x140007e64`
- `0x140008090`
- `0x140008510`
- `0x140008710`
- `0x140009344`
- `0x140009470`
- `0x14000988c`
- `0x140009cb0`
- `0x140009f88`
- `0x14000a0c8`
- `0x14000a208`
- `0x14000a340`
- `0x14000a4f4`
- `0x14000a61c`
- `0x14000a8dc`
- `0x14000aaa4`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000404c`
- `0x140004224`
- `0x140004288`
- `0x14000ae32`
- `0x14000ae60`
- `0x14000aef0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400037db`
- `KERNEL32!IsDebuggerPresent` at `0x14000389e`
- `KERNEL32!IsDebuggerPresent` at `0x1400037db`
- `KERNEL32!IsDebuggerPresent` at `0x14000389e`
- `msi!__imp_MsiCloseHandle` at `0x1400038dc`
- `msi!__imp_MsiCloseHandle` at `0x1400038dc`
- `msi!__imp_MsiCreateRecord` at `0x14000378d`
- `msi!__imp_MsiCreateRecord` at `0x14000378d`
- `msi!__imp_MsiProcessMessage` at `0x1400038cf`
- `msi!__imp_MsiProcessMessage` at `0x1400038cf`
- `msi!__imp_MsiRecordSetStringW` at `0x140003852`
- `msi!__imp_MsiRecordSetStringW` at `0x140003852`

## string_xrefs

- `0x1400037bd`: `__EHM_MsiWrite`
- `0x140003880`: `__EHM_MsiWrite`
- `0x1400037cc`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x14000388f`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`

## pseudocode

```c
__int64 DEBUGMSGBOX(const unsigned __int16 *a1, ...)
{
  __int64 v2; // rdx
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  __int64 v4; // rcx
  int v5; // r15d
  void *v6; // rcx
  MSIHANDLE v7; // esi
  MSIHANDLE v8; // ebx
  MSIHANDLE Record; // eax
  unsigned int v10; // edi
  const unsigned __int16 *v11; // r13
  bool v12; // zf
  const unsigned __int16 *v13; // rax
  __int64 v14; // r9
  __int64 v15; // r8
  signed int v16; // eax
  unsigned __int64 v18[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR szValue[4096]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+20B0h] [rbp+1FA8h] BYREF
  va_list va; // [rsp+20B0h] [rbp+1FA8h]
  va_list va1; // [rsp+20B8h] [rbp+1FB0h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v20 = va_arg(va1, _QWORD);
  memset_0(szValue, 0, sizeof(szValue));
  v18[0] = 0;
  v18[1] = 0;
  if ( (int)__EHM_AddPrefixToDebugMsg(szValue, v2, v18, a1, va) < 0 )
    return 0;
  v5 = v18[0];
  __EHM_EtwWrite(v4, v3, szValue, LODWORD(v18[0]) + 1);
  v7 = g_hMsi;
  v8 = 0;
  if ( g_hMsi )
  {
    Record = MsiCreateRecord(1u);
    v8 = Record;
    LODWORD(v18[0]) = Record;
    if ( Record )
    {
      v16 = MsiRecordSetStringW(Record, 0, szValue);
      v10 = v16;
      if ( !v16 )
      {
        MsiProcessMessage(v7, INSTALLMESSAGE_INFO, v8);
        goto LABEL_16;
      }
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      v11 = L"rc == 0L";
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        0xFAu,
        L"__EHM_MsiWrite",
        L"CBRAEx",
        L"rc == 0L",
        v10);
      v12 = !IsDebuggerPresent();
      v13 = L"CBRAEx";
      if ( !v12 )
      {
        v14 = 250;
        goto LABEL_6;
      }
      v15 = 250;
    }
    else
    {
      v10 = -2147024882;
      v11 = L"hRecord";
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        0xF7u,
        L"__EHM_MsiWrite",
        L"CPR",
        L"hRecord",
        -2147024882);
      v12 = !IsDebuggerPresent();
      v13 = L"CPR";
      if ( !v12 )
      {
        v14 = 247;
LABEL_6:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
          v14,
          L"__EHM_MsiWrite",
          v13,
          v11,
          v10,
          v18[0]);
        goto LABEL_16;
      }
      v15 = 247;
    }
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
      v15,
      L"__EHM_MsiWrite",
      v13,
      v11,
      v10);
  }
LABEL_16:
  if ( v8 )
    MsiCloseHandle(v8);
  __EHM_FlatFileWrite(v6, szValue, v5);
  return 0;
}

```

## disassembly

```asm
0x1400036d8  mov     rax, rsp
0x1400036db  mov     [rax+8], rcx
0x1400036df  mov     [rax+10h], rdx
0x1400036e3  mov     [rax+18h], r8
0x1400036e7  mov     [rax+20h], r9
0x1400036eb  push    rbp
0x1400036ec  push    rbx
0x1400036ed  push    rsi
0x1400036ee  push    rdi
0x1400036ef  push    r13
0x1400036f1  push    r14
0x1400036f3  push    r15
0x1400036f5  lea     rbp, [rax-1F98h]
0x1400036fc  mov     eax, 2060h
0x140003701  call    _alloca_probe
0x140003706  sub     rsp, rax
0x140003709  mov     rax, cs:__security_cookie
0x140003710  xor     rax, rsp
0x140003713  mov     [rbp+1F90h+var_40], rax
0x14000371a  mov     rbx, rcx
0x14000371d  xor     edx, edx; Val
0x14000371f  mov     r8d, 2000h; Size
0x140003725  lea     rcx, [rsp+2090h+szValue]; void *
0x14000372a  call    memset_0
0x14000372f  mov     [rsp+2090h+var_2050], 0
0x140003738  mov     qword ptr [rsp+2090h+var_2048], 0
0x140003741  lea     rax, [rbp+1F90h+arg_8]
0x140003748  mov     [rsp+2090h+var_2070], rax; char *
0x14000374d  mov     r9, rbx; unsigned __int16 *
0x140003750  lea     r8, [rsp+2090h+var_2050]; unsigned __int64 *
0x140003755  lea     rcx, [rsp+2090h+szValue]; unsigned __int16 *
0x14000375a  call    ?__EHM_AddPrefixToDebugMsg@@YAJPEAG_KPEA_KPEBGPEAD@Z; __EHM_AddPrefixToDebugMsg(ushort *,unsigned __int64,unsigned __int64 *,ushort const *,char *)
0x14000375f  test    eax, eax
0x140003761  js      loc_1400038EF
0x140003767  mov     r15, [rsp+2090h+var_2050]
0x14000376c  lea     r9, [r15+1]; unsigned __int64
0x140003770  lea     r8, [rsp+2090h+szValue]; unsigned __int16 *
0x140003775  call    ?__EHM_EtwWrite@@YAX_KPEBU_EVENT_DESCRIPTOR@@PEBG0@Z; __EHM_EtwWrite(unsigned __int64,_EVENT_DESCRIPTOR const *,ushort const *,unsigned __int64)
0x14000377a  mov     esi, cs:?g_hMsi@@3KA; ulong g_hMsi
0x140003780  xor     ebx, ebx
0x140003782  test    esi, esi
0x140003784  jz      loc_1400038D6
0x14000378a  lea     ecx, [rbx+1]; cParams
0x14000378d  call    cs:__imp_MsiCreateRecord
0x140003793  mov     ebx, eax
0x140003795  mov     dword ptr [rsp+2090h+var_2050], eax
0x140003799  test    eax, eax
0x14000379b  jnz     loc_140003849
0x1400037a1  mov     edi, 8007000Eh
0x1400037a6  mov     [rsp+2090h+var_2068], edi; int
0x1400037aa  lea     r13, aHrecord; "hRecord"
0x1400037b1  mov     [rsp+2090h+var_2070], r13; unsigned __int16 *
0x1400037b6  lea     r9, aCpr; "CPR"
0x1400037bd  lea     r14, aEhmMsiwrite; "__EHM_MsiWrite"
0x1400037c4  mov     r8, r14; unsigned __int16 *
0x1400037c7  mov     edx, 0F7h; unsigned int
0x1400037cc  lea     rsi, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x1400037d3  mov     rcx, rsi; unsigned __int16 *
0x1400037d6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400037db  call    cs:__imp_IsDebuggerPresent
0x1400037e1  test    eax, eax
0x1400037e3  lea     rax, aCpr; "CPR"
0x1400037ea  jz      short loc_14000381E
0x1400037ec  mov     r9d, 0F7h
0x1400037f2  mov     dword ptr [rsp+2090h+var_2058], edi
0x1400037f6  mov     qword ptr [rsp+2090h+var_2060], r13
0x1400037fb  mov     qword ptr [rsp+2090h+var_2068], rax
0x140003800  mov     [rsp+2090h+var_2070], r14
0x140003805  mov     r8, rsi
0x140003808  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000380f  mov     ecx, 2; unsigned __int8
0x140003814  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140003819  jmp     loc_1400038D6
0x14000381e  mov     r8d, 0F7h
0x140003824  mov     [rsp+2090h+var_2060], edi
0x140003828  mov     qword ptr [rsp+2090h+var_2068], r13
0x14000382d  mov     r9, r14
0x140003830  mov     [rsp+2090h+var_2070], rax
0x140003835  mov     rdx, rsi
0x140003838  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000383f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140003844  jmp     loc_1400038D6
0x140003849  lea     r8, [rsp+2090h+szValue]; szValue
0x14000384e  xor     edx, edx; iField
0x140003850  mov     ecx, ebx; hRecord
0x140003852  call    cs:__imp_MsiRecordSetStringW
0x140003858  mov     edi, eax
0x14000385a  test    eax, eax
0x14000385c  jz      short loc_1400038C5
0x14000385e  jle     short loc_140003869
0x140003860  movzx   edi, ax
0x140003863  or      edi, 80070000h
0x140003869  mov     [rsp+2090h+var_2068], edi; int
0x14000386d  lea     r13, aRc0l; "rc == 0L"
0x140003874  mov     [rsp+2090h+var_2070], r13; unsigned __int16 *
0x140003879  lea     r9, aCbraex; "CBRAEx"
0x140003880  lea     r14, aEhmMsiwrite; "__EHM_MsiWrite"
0x140003887  mov     r8, r14; unsigned __int16 *
0x14000388a  mov     edx, 0FAh; unsigned int
0x14000388f  lea     rsi, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x140003896  mov     rcx, rsi; unsigned __int16 *
0x140003899  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000389e  call    cs:__imp_IsDebuggerPresent
0x1400038a4  test    eax, eax
0x1400038a6  lea     rax, aCbraex; "CBRAEx"
0x1400038ad  jz      short loc_1400038BA
0x1400038af  mov     r9d, 0FAh
0x1400038b5  jmp     loc_1400037F2
0x1400038ba  mov     r8d, 0FAh
0x1400038c0  jmp     loc_140003824
0x1400038c5  mov     r8d, ebx; hRecord
0x1400038c8  mov     edx, 4000000h; eMessageType
0x1400038cd  mov     ecx, esi; hInstall
0x1400038cf  call    cs:__imp_MsiProcessMessage
0x1400038d5  nop
0x1400038d6  test    ebx, ebx
0x1400038d8  jz      short loc_1400038E2
0x1400038da  mov     ecx, ebx; hAny
0x1400038dc  call    cs:__imp_MsiCloseHandle
0x1400038e2  mov     r8, r15; unsigned __int64
0x1400038e5  lea     rdx, [rsp+2090h+szValue]; unsigned __int16 *
0x1400038ea  call    ?__EHM_FlatFileWrite@@YAXPEAXPEBG_K@Z; __EHM_FlatFileWrite(void *,ushort const *,unsigned __int64)
0x1400038ef  xor     eax, eax
0x1400038f1  mov     rcx, [rbp+1F90h+var_40]
0x1400038f8  xor     rcx, rsp; StackCookie
0x1400038fb  call    __security_check_cookie
0x140003900  add     rsp, 2060h
0x140003907  pop     r15
0x140003909  pop     r14
0x14000390b  pop     r13
0x14000390d  pop     rdi
0x14000390e  pop     rsi
0x14000390f  pop     rbx
0x140003910  pop     rbp
0x140003911  retn
```

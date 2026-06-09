# PlatformUtils::HasOobeCompleted(int *)

- ea: `0x14000a208`
- end: `0x14000a33a`
- name: `?HasOobeCompleted@PlatformUtils@@YAJPEAH@Z`
- size: `306`
- prototype: `__int64 __fastcall(PlatformUtils *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400029e8`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000a208`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14000a263`
- `ADVAPI32!RegGetValueW` at `0x14000a263`
- `KERNEL32!IsDebuggerPresent` at `0x14000a2b5`
- `KERNEL32!IsDebuggerPresent` at `0x14000a2b5`

## string_xrefs

- `0x14000a289`: `PlatformUtils::HasOobeCompleted`
- `0x14000a2a9`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x14000a2c3`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x14000a2f1`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x14000a22d`: `OOBECompleted`

## pseudocode

```c
__int64 __fastcall PlatformUtils::HasOobeCompleted(PlatformUtils *this, int *a2)
{
  LSTATUS ValueW; // eax
  unsigned int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+68h] [rbp+10h] BYREF
  DWORD v8; // [rsp+70h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows MultiPoint Server",
             L"OOBECompleted",
             0x10u,
             0,
             &v7,
             &v8);
  v4 = ValueW;
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
      0x2Au,
      L"PlatformUtils::HasOobeCompleted",
      L"CBRAEx",
      L"lr == 0L",
      v4);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
        42,
        L"PlatformUtils::HasOobeCompleted",
        L"CBRAEx",
        L"lr == 0L",
        v4);
    }
    else
    {
      LODWORD(v6) = v4;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
        42,
        L"PlatformUtils::HasOobeCompleted",
        L"CBRAEx",
        L"lr == 0L",
        v6);
    }
  }
  else
  {
    v4 = 0;
    *(_DWORD *)this = v7 != 0;
  }
  return v4;
}

```

## disassembly

```asm
0x14000a208  mov     r11, rsp
0x14000a20b  mov     [r11+8], rbx
0x14000a20f  mov     [r11+20h], rdi
0x14000a213  push    r12
0x14000a215  push    r14
0x14000a217  push    r15
0x14000a219  sub     rsp, 40h
0x14000a21d  lea     rax, [r11+18h]
0x14000a221  mov     [rsp+58h+arg_8], 0
0x14000a229  mov     [r11-28h], rax
0x14000a22d  lea     r8, aOobecompleted; "OOBECompleted"
0x14000a234  lea     rax, [r11+10h]
0x14000a238  mov     [rsp+58h+arg_10], 4
0x14000a240  mov     rdi, rcx
0x14000a243  mov     [r11-30h], rax
0x14000a247  mov     r9d, 10h; dwFlags
0x14000a24d  mov     qword ptr [r11-38h], 0
0x14000a255  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14000a25c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000a263  call    cs:__imp_RegGetValueW
0x14000a269  mov     ebx, eax
0x14000a26b  test    eax, eax
0x14000a26d  jz      loc_14000A316
0x14000a273  jle     short loc_14000A27E
0x14000a275  movzx   ebx, ax
0x14000a278  or      ebx, 80070000h
0x14000a27e  lea     r12, aCbraex; "CBRAEx"
0x14000a285  mov     [rsp+58h+var_30], ebx; int
0x14000a289  lea     r14, aPlatformutilsH; "PlatformUtils::HasOobeCompleted"
0x14000a290  mov     edi, 2Ah ; '*'
0x14000a295  lea     r15, aLr0l; "lr == 0L"
0x14000a29c  mov     r9, r12; unsigned __int16 *
0x14000a29f  mov     r8, r14; unsigned __int16 *
0x14000a2a2  mov     [rsp+58h+var_38], r15; unsigned __int16 *
0x14000a2a7  mov     edx, edi; unsigned int
0x14000a2a9  lea     rcx, aTermsrvWmsSrcC_0; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a2b0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a2b5  call    cs:__imp_IsDebuggerPresent
0x14000a2bb  test    eax, eax
0x14000a2bd  jz      short loc_14000A2ED
0x14000a2bf  mov     [rsp+58h+var_20], ebx
0x14000a2c3  lea     r8, aTermsrvWmsSrcC_0; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a2ca  mov     [rsp+58h+var_28], r15
0x14000a2cf  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000a2d6  mov     qword ptr [rsp+58h+var_30], r12
0x14000a2db  lea     ecx, [rdi-28h]; unsigned __int8
0x14000a2de  mov     r9d, edi
0x14000a2e1  mov     [rsp+58h+var_38], r14
0x14000a2e6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000a2eb  jmp     short loc_14000A323
0x14000a2ed  mov     dword ptr [rsp+58h+var_28], ebx
0x14000a2f1  lea     rdx, aTermsrvWmsSrcC_0; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a2f8  mov     qword ptr [rsp+58h+var_30], r15
0x14000a2fd  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000a304  mov     r9, r14
0x14000a307  mov     [rsp+58h+var_38], r12
0x14000a30c  mov     r8d, edi
0x14000a30f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000a314  jmp     short loc_14000A323
0x14000a316  xor     ecx, ecx
0x14000a318  xor     ebx, ebx
0x14000a31a  cmp     [rsp+58h+arg_8], ecx
0x14000a31e  setnz   cl
0x14000a321  mov     [rdi], ecx
0x14000a323  mov     rdi, [rsp+58h+arg_18]
0x14000a328  mov     eax, ebx
0x14000a32a  mov     rbx, [rsp+58h+arg_0]
0x14000a32f  add     rsp, 40h
0x14000a333  pop     r15
0x14000a335  pop     r14
0x14000a337  pop     r12
0x14000a339  retn
```

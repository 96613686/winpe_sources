# MergeSdbMigXml(ushort * *,ushort const *,void *)

- ea: `0x18003ca80`
- end: `0x18003cc36`
- name: `?MergeSdbMigXml@@YAJPEAPEAGPEBGPEAX@Z`
- size: `438`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001cf0`
- `0x18000a5e0`
- `0x18000b720`
- `0x18000c190`
- `0x18000e064`
- `0x18003ca80`
- `0x18003cc3c`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003cb62`
- `ntdll!RtlAllocateHeap` at `0x18003cb62`
- `ntdll!RtlFreeHeap` at `0x18003cbd7`
- `ntdll!RtlFreeHeap` at `0x18003cbd7`

## string_xrefs

- `0x18003cacf`: `<component type="Application" context="UserAndSystem">                                                                                              \n    <displayName>MergeSdb Migration Data</displayName>                                                                                                  \n        <role role="Settings">                                                                                                                        \n            <rules context = "System">   `
- `0x18003caf2`: `msimain.sdb`
- `0x18003cbe7`: `[MergeSdbShim] Failed to populate migxml for sdb [%x]`
- `0x18003cbb4`: `MergeSdbMigXml`
- `0x18003cbf8`: `MergeSdbMigXml`
- `0x18003cb1c`: `                </objectSet>                                                                                                                            \n                </include>                                                                                                                              \n            </rules>                                                                                                                                    \n        </role>                    `
- `0x18003cb75`: `[MergeSdbShim] Failed to allocate migxml buffer [%x]`
- `0x18003cba7`: `[MergeSdbShim] Failed to copy migxml to buffer [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MergeSdbMigXml(unsigned __int16 **a1, const unsigned __int16 *a2, void *a3)
{
  unsigned int i; // edi
  const wchar_t *v5; // rdx
  int v6; // ebx
  unsigned __int16 **v7; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // rbx
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v11; // rdi
  const unsigned __int16 *v12; // r8
  int v13; // eax
  unsigned __int16 *Src[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h]
  unsigned __int64 v17; // [rsp+50h] [rbp-10h]

  *(_OWORD *)Src = 0;
  v16 = 0;
  v17 = 7;
  LOWORD(Src[0]) = 0;
  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
  for ( i = 0; i < 2; ++i )
  {
    if ( i )
      v5 = L"msimain.sdb";
    else
      v5 = L"sysmain.sdb";
    v6 = PopulateForSdb(Src, v5);
    if ( v6 < 0 )
    {
      AslLogCallPrintf(1, "MergeSdbMigXml", 243, "[MergeSdbShim] Failed to populate migxml for sdb [%x]", v6);
      goto LABEL_19;
    }
  }
  std::wstring::append(
    Src,
    L"                </objectSet>                                                                                        "
     "                                    \r\n"
     "                </include>                                                                                         "
     "                                     \r\n"
     "            </rules>                                                                                               "
     "                                     \r\n"
     "        </role>                                                                                                    "
     "                                     \r\n"
     "</component>");
  v7 = Src;
  if ( v17 > 7 )
    v7 = (unsigned __int16 **)Src[0];
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)v7 + v8) );
  v9 = v8 + 1;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (v8 + 1));
  v11 = Heap;
  if ( Heap )
  {
    v12 = (const unsigned __int16 *)Src;
    if ( v17 > 7 )
      v12 = Src[0];
    v13 = StringCchCopyW(Heap, v9, v12);
    v6 = v13;
    if ( v13 >= 0 )
    {
      *a1 = v11;
      v6 = 0;
    }
    else
    {
      AslLogCallPrintf(1, "MergeSdbMigXml", 264, "[MergeSdbShim] Failed to copy migxml to buffer [%x]", v13);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    }
  }
  else
  {
    v6 = -2147024882;
    AslLogCallPrintf(1, "MergeSdbMigXml", 257, "[MergeSdbShim] Failed to allocate migxml buffer [%x]", -2147024882);
  }
LABEL_19:
  std::wstring::~wstring(Src);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003ca80  mov     rax, rsp
0x18003ca83  push    rbp
0x18003ca84  push    rdi
0x18003ca85  push    r14
0x18003ca87  mov     rbp, rsp
0x18003ca8a  sub     rsp, 60h
0x18003ca8e  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18003ca96  mov     [rax+10h], rbx
0x18003ca9a  mov     [rax+18h], rsi
0x18003ca9e  mov     rax, cs:__security_cookie
0x18003caa5  xor     rax, rsp
0x18003caa8  mov     [rbp+var_8], rax
0x18003caac  mov     rsi, rcx
0x18003caaf  mov     ebx, 80004005h
0x18003cab4  xorps   xmm0, xmm0
0x18003cab7  movups  xmmword ptr [rbp+Src], xmm0
0x18003cabb  xor     r14d, r14d
0x18003cabe  mov     [rbp+var_18], r14
0x18003cac2  mov     [rbp+var_10], 7
0x18003caca  mov     word ptr [rbp+Src], r14w
0x18003cacf  lea     r9, aComponentTypeA
0x18003cad6  mov     edx, 4BAh
0x18003cadb  lea     rcx, [rbp+Src]
0x18003cadf  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z
0x18003cae4  mov     edi, r14d
0x18003cae7  mov     eax, edi
0x18003cae9  test    edi, edi
0x18003caeb  jz      short loc_18003CAFB
0x18003caed  cmp     eax, 1
0x18003caf0  jnz     short loc_18003CB0D
0x18003caf2  lea     rdx, aMsimainSdb
0x18003caf9  jmp     short loc_18003CB02
0x18003cafb  lea     rdx, aSysmainSdb
0x18003cb02  lea     rcx, [rbp+Src]; Src
0x18003cb06  call    ?PopulateForSdb@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z
0x18003cb0b  mov     ebx, eax
0x18003cb0d  test    ebx, ebx
0x18003cb0f  js      loc_18003CBE7
0x18003cb15  inc     edi
0x18003cb17  cmp     edi, 2
0x18003cb1a  jb      short loc_18003CAE7
0x18003cb1c  lea     rdx, aObjectset
0x18003cb23  lea     rcx, [rbp+Src]; Src
0x18003cb27  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z
0x18003cb2c  lea     rcx, [rbp+Src]
0x18003cb30  cmp     [rbp+var_10], 7
0x18003cb35  cmova   rcx, [rbp+Src]
0x18003cb3a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003cb3e  inc     rax
0x18003cb41  cmp     [rcx+rax*2], r14w
0x18003cb46  jnz     short loc_18003CB3E
0x18003cb48  lea     rbx, [rax+1]
0x18003cb4c  lea     r8, [rbx+rbx]; Size
0x18003cb50  mov     rcx, gs:60h
0x18003cb59  mov     edx, 8; Flags
0x18003cb5e  mov     rcx, [rcx+30h]; HeapHandle
0x18003cb62  call    cs:__imp_RtlAllocateHeap
0x18003cb68  mov     rdi, rax
0x18003cb6b  test    rax, rax
0x18003cb6e  jnz     short loc_18003CB84
0x18003cb70  mov     ebx, 8007000Eh
0x18003cb75  lea     r9, aMergesdbshimFa_5
0x18003cb7c  mov     r8d, 101h
0x18003cb82  jmp     short loc_18003CBF4
0x18003cb84  lea     r8, [rbp+Src]
0x18003cb88  cmp     [rbp+var_10], 7
0x18003cb8d  cmova   r8, [rbp+Src]; unsigned __int16 *
0x18003cb92  mov     rdx, rbx; unsigned __int64
0x18003cb95  mov     rcx, rdi; unsigned __int16 *
0x18003cb98  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x18003cb9d  mov     ebx, eax
0x18003cb9f  test    eax, eax
0x18003cba1  jns     short loc_18003CBDF
0x18003cba3  mov     [rsp+60h+var_40], eax
0x18003cba7  lea     r9, aMergesdbshimFa_1
0x18003cbae  mov     r8d, 108h
0x18003cbb4  lea     rdx, aMergesdbmigxml
0x18003cbbb  mov     ecx, 1
0x18003cbc0  call    AslLogCallPrintf
0x18003cbc5  mov     rcx, gs:60h
0x18003cbce  mov     r8, rdi; P
0x18003cbd1  xor     edx, edx; Flags
0x18003cbd3  mov     rcx, [rcx+30h]; HeapHandle
0x18003cbd7  call    cs:__imp_RtlFreeHeap
0x18003cbdd  jmp     short loc_18003CC0A
0x18003cbdf  mov     [rsi], rdi
0x18003cbe2  mov     ebx, r14d
0x18003cbe5  jmp     short loc_18003CC0A
0x18003cbe7  lea     r9, aMergesdbshimFa_2
0x18003cbee  mov     r8d, 0F3h
0x18003cbf4  mov     [rsp+60h+var_40], ebx
0x18003cbf8  lea     rdx, aMergesdbmigxml
0x18003cbff  mov     ecx, 1
0x18003cc04  call    AslLogCallPrintf
0x18003cc09  nop
0x18003cc0a  lea     rcx, [rbp+Src]; void *
0x18003cc0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18003cc13  mov     eax, ebx
0x18003cc15  mov     rcx, [rbp+var_8]
0x18003cc19  xor     rcx, rsp; StackCookie
0x18003cc1c  call    __security_check_cookie
0x18003cc21  lea     r11, [rsp+60h+var_s0]
0x18003cc26  mov     rbx, [r11+28h]
0x18003cc2a  mov     rsi, [r11+30h]
0x18003cc2e  mov     rsp, r11
0x18003cc31  pop     r14
0x18003cc33  pop     rdi
0x18003cc34  pop     rbp
0x18003cc35  retn
```

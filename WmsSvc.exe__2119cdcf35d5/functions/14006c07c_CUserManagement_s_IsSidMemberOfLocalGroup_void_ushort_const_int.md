# CUserManagement::s_IsSidMemberOfLocalGroup(void *,ushort const *,int *)

- ea: `0x14006c07c`
- end: `0x14006c25c`
- name: `?s_IsSidMemberOfLocalGroup@CUserManagement@@CAJPEAXPEBGPEAH@Z`
- size: `480`
- prototype: `__int64 __fastcall(PSID pSid1, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004e600`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006c07c`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x14006c21b`
- `ADVAPI32!EqualSid` at `0x14006c21b`
- `KERNEL32!IsDebuggerPresent` at `0x14006c134`
- `KERNEL32!IsDebuggerPresent` at `0x14006c1e5`
- `KERNEL32!IsDebuggerPresent` at `0x14006c134`
- `KERNEL32!IsDebuggerPresent` at `0x14006c1e5`
- `NETAPI32!NetLocalGroupGetMembers` at `0x14006c0e1`
- `NETAPI32!NetLocalGroupGetMembers` at `0x14006c0e1`
- `NETAPI32!NetApiBufferFree` at `0x14006c23f`
- `NETAPI32!NetApiBufferFree` at `0x14006c23f`

## string_xrefs

- `0x14006c111`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006c1bf`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006c107`: `CUserManagement::s_IsSidMemberOfLocalGroup`
- `0x14006c1b4`: `CUserManagement::s_IsSidMemberOfLocalGroup`
- `0x14006c1c9`: `cEntriesRead == cTotalEntries`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_IsSidMemberOfLocalGroup(PSID pSid1, const unsigned __int16 *a2, int *a3)
{
  signed int Members; // eax
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // r12
  __int64 v8; // r9
  __int64 v9; // r8
  DWORD v10; // eax
  __int64 v11; // rdi
  __int64 v13; // [rsp+30h] [rbp-38h]
  __int64 v14; // [rsp+38h] [rbp-30h]
  LPVOID Buffer; // [rsp+40h] [rbp-28h] BYREF
  DWORD v16; // [rsp+78h] [rbp+10h] BYREF
  int v17; // [rsp+7Ch] [rbp+14h]
  DWORD v18; // [rsp+88h] [rbp+20h] BYREF

  v17 = HIDWORD(a2);
  Buffer = 0;
  v16 = 0;
  v18 = 0;
  Members = NetLocalGroupGetMembers(0, L"WmsOperators", 0, (LPBYTE *)&Buffer, 0xFFFFFFFF, &v16, &v18, 0);
  v6 = Members;
  if ( Members )
  {
    if ( Members > 0 )
      v6 = (unsigned __int16)Members | 0x80070000;
    v7 = L"nStatus == 0";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x49Du,
      L"CUserManagement::s_IsSidMemberOfLocalGroup",
      L"CBRAEx",
      L"nStatus == 0",
      v6);
    if ( IsDebuggerPresent() )
    {
      v8 = 1181;
LABEL_6:
      LODWORD(v14) = v6;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        v8,
        L"CUserManagement::s_IsSidMemberOfLocalGroup",
        L"CBRAEx",
        v7,
        v14);
      goto LABEL_18;
    }
    v9 = 1181;
LABEL_8:
    LODWORD(v13) = v6;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      v9,
      L"CUserManagement::s_IsSidMemberOfLocalGroup",
      L"CBRAEx",
      v7,
      v13);
    goto LABEL_18;
  }
  v10 = v16;
  if ( v16 != v18 )
  {
    v6 = -2147418113;
    v7 = L"cEntriesRead == cTotalEntries";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x49Eu,
      L"CUserManagement::s_IsSidMemberOfLocalGroup",
      L"CBRAEx",
      L"cEntriesRead == cTotalEntries",
      -2147418113);
    if ( IsDebuggerPresent() )
    {
      v8 = 1182;
      goto LABEL_6;
    }
    v9 = 1182;
    goto LABEL_8;
  }
  v6 = 0;
  v11 = 0;
  *a3 = 0;
  if ( v10 )
  {
    while ( !EqualSid(pSid1, *((PSID *)Buffer + v11)) )
    {
      v11 = (unsigned int)(v11 + 1);
      if ( v16 <= (unsigned int)v11 )
        goto LABEL_18;
    }
    *a3 = 1;
  }
LABEL_18:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  return v6;
}

```

## disassembly

```asm
0x14006c07c  mov     r11, rsp
0x14006c07f  mov     [r11+8], rbx
0x14006c083  mov     [r11+18h], rbp
0x14006c087  mov     [r11+10h], rdx
0x14006c08b  push    rsi
0x14006c08c  push    rdi
0x14006c08d  push    r12
0x14006c08f  sub     rsp, 50h
0x14006c093  mov     qword ptr [r11-30h], 0
0x14006c09b  lea     rax, [r11+20h]
0x14006c09f  mov     [r11-38h], rax
0x14006c0a3  lea     r9, [r11-28h]; bufptr
0x14006c0a7  lea     rax, [r11+10h]
0x14006c0ab  mov     qword ptr [r11-28h], 0
0x14006c0b3  mov     rsi, r8
0x14006c0b6  mov     [r11-40h], rax
0x14006c0ba  mov     rbp, rcx
0x14006c0bd  mov     [rsp+68h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x14006c0c5  xor     r8d, r8d; level
0x14006c0c8  mov     [rsp+68h+arg_8], 0
0x14006c0d0  lea     rdx, localgroupname; "WmsOperators"
0x14006c0d7  mov     dword ptr [r11+20h], 0
0x14006c0df  xor     ecx, ecx; servername
0x14006c0e1  call    cs:__imp_NetLocalGroupGetMembers
0x14006c0e7  mov     ebx, eax
0x14006c0e9  test    eax, eax
0x14006c0eb  jz      loc_14006C19B
0x14006c0f1  jle     short loc_14006C0FC
0x14006c0f3  movzx   ebx, ax
0x14006c0f6  or      ebx, 80070000h
0x14006c0fc  lea     rbp, aCbraex; "CBRAEx"
0x14006c103  mov     [rsp+68h+var_40], ebx; int
0x14006c107  lea     rsi, aCusermanagemen_3; "CUserManagement::s_IsSidMemberOfLocalGr"...
0x14006c10e  mov     r9, rbp; unsigned __int16 *
0x14006c111  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006c118  mov     r8, rsi; unsigned __int16 *
0x14006c11b  lea     r12, aNstatus0; "nStatus == 0"
0x14006c122  mov     rcx, rdi; unsigned __int16 *
0x14006c125  mov     edx, 49Dh; unsigned int
0x14006c12a  mov     qword ptr [rsp+68h+prefmaxlen], r12; unsigned __int16 *
0x14006c12f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006c134  call    cs:__imp_IsDebuggerPresent
0x14006c13a  test    eax, eax
0x14006c13c  jz      short loc_14006C170
0x14006c13e  mov     r9d, 49Dh
0x14006c144  mov     dword ptr [rsp+68h+var_30], ebx
0x14006c148  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006c14f  mov     [rsp+68h+var_38], r12
0x14006c154  mov     r8, rdi
0x14006c157  mov     qword ptr [rsp+68h+var_40], rbp
0x14006c15c  mov     ecx, 2; unsigned __int8
0x14006c161  mov     qword ptr [rsp+68h+prefmaxlen], rsi
0x14006c166  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006c16b  jmp     loc_14006C235
0x14006c170  mov     r8d, 49Dh
0x14006c176  mov     dword ptr [rsp+68h+var_38], ebx
0x14006c17a  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006c181  mov     qword ptr [rsp+68h+var_40], r12
0x14006c186  mov     r9, rsi
0x14006c189  mov     rdx, rdi
0x14006c18c  mov     qword ptr [rsp+68h+prefmaxlen], rbp
0x14006c191  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006c196  jmp     loc_14006C235
0x14006c19b  mov     eax, [rsp+68h+arg_8]
0x14006c19f  cmp     eax, [rsp+68h+arg_18]
0x14006c1a6  jz      short loc_14006C205
0x14006c1a8  mov     ebx, 8000FFFFh
0x14006c1ad  lea     rbp, aCbraex; "CBRAEx"
0x14006c1b4  lea     rsi, aCusermanagemen_3; "CUserManagement::s_IsSidMemberOfLocalGr"...
0x14006c1bb  mov     [rsp+68h+var_40], ebx; int
0x14006c1bf  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006c1c6  mov     r9, rbp; unsigned __int16 *
0x14006c1c9  lea     r12, aCentriesreadCt; "cEntriesRead == cTotalEntries"
0x14006c1d0  mov     r8, rsi; unsigned __int16 *
0x14006c1d3  mov     rcx, rdi; unsigned __int16 *
0x14006c1d6  mov     qword ptr [rsp+68h+prefmaxlen], r12; unsigned __int16 *
0x14006c1db  mov     edx, 49Eh; unsigned int
0x14006c1e0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006c1e5  call    cs:__imp_IsDebuggerPresent
0x14006c1eb  test    eax, eax
0x14006c1ed  jz      short loc_14006C1FA
0x14006c1ef  mov     r9d, 49Eh
0x14006c1f5  jmp     loc_14006C144
0x14006c1fa  mov     r8d, 49Eh
0x14006c200  jmp     loc_14006C176
0x14006c205  xor     ebx, ebx
0x14006c207  xor     edi, edi
0x14006c209  mov     [rsi], ebx
0x14006c20b  test    eax, eax
0x14006c20d  jz      short loc_14006C235
0x14006c20f  mov     rdx, [rsp+68h+Buffer]
0x14006c214  mov     rcx, rbp; pSid1
0x14006c217  mov     rdx, [rdx+rdi*8]; pSid2
0x14006c21b  call    cs:__imp_EqualSid
0x14006c221  test    eax, eax
0x14006c223  jnz     short loc_14006C22F
0x14006c225  inc     edi
0x14006c227  cmp     [rsp+68h+arg_8], edi
0x14006c22b  ja      short loc_14006C20F
0x14006c22d  jmp     short loc_14006C235
0x14006c22f  mov     dword ptr [rsi], 1
0x14006c235  mov     rcx, [rsp+68h+Buffer]; Buffer
0x14006c23a  test    rcx, rcx
0x14006c23d  jz      short loc_14006C245
0x14006c23f  call    cs:__imp_NetApiBufferFree
0x14006c245  lea     r11, [rsp+68h+var_18]
0x14006c24a  mov     eax, ebx
0x14006c24c  mov     rbx, [r11+20h]
0x14006c250  mov     rbp, [r11+30h]
0x14006c254  mov     rsp, r11
0x14006c257  pop     r12
0x14006c259  pop     rdi
0x14006c25a  pop     rsi
0x14006c25b  retn
```

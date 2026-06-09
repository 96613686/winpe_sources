# CUserManagement::s_DoesUserExist(ushort const *,int *)

- ea: `0x14000a4f4`
- end: `0x14000a615`
- name: `?s_DoesUserExist@CUserManagement@@SAJPEBGPEAH@Z`
- size: `289`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006e24`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000a4f4`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000a584`
- `KERNEL32!IsDebuggerPresent` at `0x14000a584`
- `NETAPI32!NetApiBufferFree` at `0x14000a5ff`
- `NETAPI32!NetApiBufferFree` at `0x14000a5ff`
- `NETAPI32!NetUserGetInfo` at `0x14000a523`
- `NETAPI32!NetUserGetInfo` at `0x14000a523`

## string_xrefs

- `0x14000a576`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14000a592`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14000a5c2`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_DoesUserExist(const unsigned __int16 *a1, int *a2)
{
  signed int Info; // eax
  unsigned int v4; // ebx
  unsigned int v5; // edi
  unsigned int v7; // [rsp+30h] [rbp-48h]
  unsigned int v8; // [rsp+38h] [rbp-40h]
  LPVOID Buffer; // [rsp+80h] [rbp+8h] BYREF

  Buffer = 0;
  Info = NetUserGetInfo(0, L"WmsShell", 0, (LPBYTE *)&Buffer);
  v4 = Info;
  if ( !Info || Info == 2221 )
  {
    v5 = 0;
    *a2 = Info == 0;
  }
  else
  {
    if ( Info > 0 )
      v4 = (unsigned __int16)Info | 0x80070000;
    v5 = v4;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      192,
      L"CUserManagement::s_DoesUserExist",
      L"CBRAEx",
      L"nStatus == 0 || nStatus == (2100+121)",
      v4);
    if ( IsDebuggerPresent() )
    {
      v8 = v4;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        192,
        L"CUserManagement::s_DoesUserExist",
        L"CBRAEx",
        L"nStatus == 0 || nStatus == (2100+121)",
        v8);
    }
    else
    {
      v7 = v4;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        192,
        L"CUserManagement::s_DoesUserExist",
        L"CBRAEx",
        L"nStatus == 0 || nStatus == (2100+121)",
        v7);
    }
  }
  if ( Buffer )
    NetApiBufferFree(Buffer);
  return v5;
}

```

## disassembly

```asm
0x14000a4f4  mov     rax, rsp
0x14000a4f7  mov     [rax+8], rcx
0x14000a4fb  push    rbx
0x14000a4fc  push    rsi
0x14000a4fd  push    rdi
0x14000a4fe  push    r12
0x14000a500  push    r14
0x14000a502  push    r15
0x14000a504  sub     rsp, 48h
0x14000a508  mov     rsi, rdx
0x14000a50b  mov     qword ptr [rax+8], 0
0x14000a513  lea     rdx, username; "WmsShell"
0x14000a51a  xor     r8d, r8d; level
0x14000a51d  lea     r9, [rax+8]; bufptr
0x14000a521  xor     ecx, ecx; servername
0x14000a523  call    cs:__imp_NetUserGetInfo
0x14000a529  mov     ebx, eax
0x14000a52b  test    eax, eax
0x14000a52d  jz      loc_14000A5E7
0x14000a533  cmp     eax, 8ADh
0x14000a538  jz      loc_14000A5E7
0x14000a53e  test    eax, eax
0x14000a540  jle     short loc_14000A54B
0x14000a542  movzx   ebx, ax
0x14000a545  or      ebx, 80070000h
0x14000a54b  lea     r12, aCbraex; "CBRAEx"
0x14000a552  mov     [rsp+78h+var_50], ebx; int
0x14000a556  lea     r14, aCusermanagemen; "CUserManagement::s_DoesUserExist"
0x14000a55d  mov     esi, 0C0h
0x14000a562  lea     r15, aNstatus0Nstatu; "nStatus == 0 || nStatus == (2100+121)"
0x14000a569  mov     r9, r12; unsigned __int16 *
0x14000a56c  mov     r8, r14; unsigned __int16 *
0x14000a56f  mov     [rsp+78h+var_58], r15; unsigned __int16 *
0x14000a574  mov     edx, esi; unsigned int
0x14000a576  lea     rcx, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14000a57d  mov     edi, ebx
0x14000a57f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a584  call    cs:__imp_IsDebuggerPresent
0x14000a58a  test    eax, eax
0x14000a58c  jz      short loc_14000A5BE
0x14000a58e  mov     [rsp+78h+var_40], ebx
0x14000a592  lea     r8, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14000a599  mov     [rsp+78h+var_48], r15
0x14000a59e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000a5a5  mov     qword ptr [rsp+78h+var_50], r12
0x14000a5aa  mov     r9d, esi
0x14000a5ad  mov     ecx, 2; unsigned __int8
0x14000a5b2  mov     [rsp+78h+var_58], r14
0x14000a5b7  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000a5bc  jmp     short loc_14000A5F2
0x14000a5be  mov     dword ptr [rsp+78h+var_48], ebx
0x14000a5c2  lea     rdx, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14000a5c9  mov     qword ptr [rsp+78h+var_50], r15
0x14000a5ce  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000a5d5  mov     r9, r14
0x14000a5d8  mov     [rsp+78h+var_58], r12
0x14000a5dd  mov     r8d, esi
0x14000a5e0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000a5e5  jmp     short loc_14000A5F2
0x14000a5e7  xor     ecx, ecx
0x14000a5e9  xor     edi, edi
0x14000a5eb  test    eax, eax
0x14000a5ed  setz    cl
0x14000a5f0  mov     [rsi], ecx
0x14000a5f2  mov     rcx, [rsp+78h+Buffer]; Buffer
0x14000a5fa  test    rcx, rcx
0x14000a5fd  jz      short loc_14000A605
0x14000a5ff  call    cs:__imp_NetApiBufferFree
0x14000a605  mov     eax, edi
0x14000a607  add     rsp, 48h
0x14000a60b  pop     r15
0x14000a60d  pop     r14
0x14000a60f  pop     r12
0x14000a611  pop     rdi
0x14000a612  pop     rsi
0x14000a613  pop     rbx
0x14000a614  retn
```

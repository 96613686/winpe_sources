# LoadRegTypeLibOfSzGuidLookup_WithSyskind

- ea: `0x180059124`
- end: `0x1800591ea`
- name: `LoadRegTypeLibOfSzGuidLookup_WithSyskind`
- size: `198`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180059664`
- `0x18005ebd0`
- `0x1800617c0`

## callees

- `0x180014840`
- `0x180015c44`
- `0x18004d900`
- `0x180059124`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180059168`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180059168`

## pseudocode

```c
__int64 __fastcall LoadRegTypeLibOfSzGuidLookup_WithSyskind(
        OLECHAR *a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned int a4,
        int a5,
        int a6,
        ITypeLib **a7)
{
  struct ITypeLib *v11; // rax
  CLSID pclsid[2]; // [rsp+50h] [rbp-58h] BYREF

  memset(pclsid, 0, 28);
  CLSIDFromString(a1, pclsid);
  pclsid[1].Data1 = a4;
  *(_WORD *)pclsid[1].Data4 = a2;
  *(_WORD *)&pclsid[1].Data4[2] = a3;
  *(_DWORD *)&pclsid[1].Data2 = 3;
  v11 = OLE_TYPEMGR::LookupRefdTypeLib(g_poletmgr, (struct REFLIBATTR *)pclsid);
  *a7 = v11;
  if ( v11 )
    return 0;
  else
    return LoadRegTypeLibOfSzGuid_WithSyskind((ITypeLib *)a1, a2, a3, a4, 0, 0, 3, a7, 0);
}

```

## disassembly

```asm
0x180059124  push    rbx
0x180059126  push    rbp
0x180059127  push    rsi
0x180059128  push    rdi
0x180059129  push    r14
0x18005912b  sub     rsp, 80h
0x180059132  mov     rax, cs:__security_cookie
0x180059139  xor     rax, rsp
0x18005913c  mov     [rsp+0A8h+var_38], rax
0x180059141  mov     r14, [rsp+0A8h+arg_30]
0x180059149  xorps   xmm0, xmm0
0x18005914c  movzx   edi, dx
0x18005914f  mov     ebp, r9d
0x180059152  movups  xmmword ptr [rsp+0A8h+pclsid.Data1], xmm0
0x180059157  lea     rdx, [rsp+0A8h+pclsid]; pclsid
0x18005915c  movzx   esi, r8w
0x180059160  movups  xmmword ptr [rsp+0A8h+pclsid.Data4+4], xmm0
0x180059165  mov     rbx, rcx
0x180059168  call    cs:__imp_CLSIDFromString
0x18005916e  mov     rcx, cs:?g_poletmgr@@3PEAVOLE_TYPEMGR@@EA; this
0x180059175  lea     rdx, [rsp+0A8h+pclsid]; struct REFLIBATTR *
0x18005917a  mov     [rsp+0A8h+var_48], ebp
0x18005917e  mov     [rsp+0A8h+var_40], di
0x180059183  mov     [rsp+0A8h+var_3E], si
0x180059188  mov     [rsp+0A8h+var_44], 3
0x180059190  call    ?LookupRefdTypeLib@OLE_TYPEMGR@@QEAAPEAUITypeLib@@PEAUREFLIBATTR@@@Z; OLE_TYPEMGR::LookupRefdTypeLib(REFLIBATTR *)
0x180059195  xor     ecx, ecx
0x180059197  mov     [r14], rax
0x18005919a  test    rax, rax
0x18005919d  jz      short loc_1800591A3
0x18005919f  xor     eax, eax
0x1800591a1  jmp     short loc_1800591CF
0x1800591a3  mov     [rsp+0A8h+var_68], cl
0x1800591a7  mov     r9d, ebp
0x1800591aa  mov     [rsp+0A8h+var_70], r14
0x1800591af  movzx   r8d, si
0x1800591b3  mov     [rsp+0A8h+var_78], 3
0x1800591bb  movzx   edx, di
0x1800591be  mov     [rsp+0A8h+var_80], rcx
0x1800591c3  mov     [rsp+0A8h+var_88], ecx
0x1800591c7  mov     rcx, rbx
0x1800591ca  call    LoadRegTypeLibOfSzGuid_WithSyskind
0x1800591cf  mov     rcx, [rsp+0A8h+var_38]
0x1800591d4  xor     rcx, rsp; StackCookie
0x1800591d7  call    __security_check_cookie
0x1800591dc  add     rsp, 80h
0x1800591e3  pop     r14
0x1800591e5  pop     rdi
0x1800591e6  pop     rsi
0x1800591e7  pop     rbp
0x1800591e8  pop     rbx
0x1800591e9  retn
```

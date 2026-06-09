# CAppConfig::Init(CIsapiReqInfo *,CAppln *)

- ea: `0x180002864`
- end: `0x180002a32`
- name: `?Init@CAppConfig@@QEAAJPEAVCIsapiReqInfo@@PEAVCAppln@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(CAppConfig *__hidden this, struct CIsapiReqInfo *, struct CAppln *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001400`
- `0x1800054e8`

## callees

- `0x180002864`
- `0x180002a38`
- `0x180003314`
- `0x180006e24`
- `0x180064010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x1800029a5`
- `ole32!CLSIDFromString` at `0x1800029a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029c8`
- `KERNEL32!GetLastError` at `0x18000289b`
- `KERNEL32!GetLastError` at `0x18000289b`
- `iisutil!IISInitializeCriticalSection` at `0x180002891`
- `iisutil!IISInitializeCriticalSection` at `0x180002891`

## pseudocode

```c
__int64 __fastcall CAppConfig::Init(CAppConfig *this, struct CIsapiReqInfo *a2, struct CAppln *a3)
{
  int ConfigFromSystem; // esi
  signed int LastError; // eax
  CScriptManager *v8; // rcx
  _BYTE *v9; // r8
  __int64 v10; // rdx
  signed int i; // r9d
  int v12; // eax
  OLECHAR *v13; // r14
  LPCOLESTR lpsz; // [rsp+88h] [rbp+20h] BYREF

  ConfigFromSystem = 0;
  if ( !(unsigned int)IISInitializeCriticalSection((char *)this + 152) )
  {
    LastError = GetLastError();
    ConfigFromSystem = LastError;
    if ( LastError > 0 )
      ConfigFromSystem = (unsigned __int16)LastError | 0x80070000;
  }
  if ( ConfigFromSystem >= 0 )
  {
    *((_DWORD *)this + 3) |= 0x10u;
    *(_QWORD *)this = a3;
    ConfigFromSystem = ReadConfigFromSystem(this);
    if ( ConfigFromSystem >= 0 )
    {
      *((_DWORD *)this + 3) = *((_DWORD *)this + 3) & 0xFFFFFFFB
                            | (4
                             * (CScriptManager::ProgLangIdOfLangName(
                                  v8,
                                  *((const char **)this + 25),
                                  (struct _GUID *)((char *)this + 68)) >= 0));
      ConfigFromSystem = 0;
    }
    if ( ConfigFromSystem >= 0 )
    {
      v9 = (_BYTE *)*((_QWORD *)this + 26);
      if ( v9 )
      {
        lpsz = 0;
        v10 = -1;
        do
          ++v10;
        while ( v9[v10] );
        if ( *v9 == 123 && (unsigned int)v10 > 2 )
        {
          for ( i = 1; i < (unsigned int)(v10 - 1); ++i )
            v9[i - 1] = v9[i];
          v9[(unsigned int)(v10 - 2)] = 0;
        }
        v12 = SysAllocStringFromSz(*((LPCCH *)this + 26), v10, (unsigned __int16 **)&lpsz, 0);
        v13 = (OLECHAR *)lpsz;
        if ( v12 >= 0 )
          *((_DWORD *)this + 3) = *((_DWORD *)this + 3) & 0xFFFFFFF7
                                | (8 * (CLSIDFromString(lpsz, (LPCLSID)((char *)this + 100)) >= 0));
        ConfigFromSystem = 0;
        if ( v13 )
          SysFreeString(v13);
      }
      if ( *((_DWORD *)this + 32)
        && !(*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, char *, _QWORD))(*((_QWORD *)a2 + 1) + 184LL))(
              *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL),
              1041,
              *((_QWORD *)a3 + 15),
              (char *)this + 136,
              0) )
      {
        *((_QWORD *)this + 17) = -1;
      }
    }
    *((_DWORD *)this + 3) |= 1u;
    *((_DWORD *)this + 2) = 0;
  }
  return (unsigned int)ConfigFromSystem;
}

```

## disassembly

```asm
0x180002864  mov     [rsp+arg_10], r8
0x180002869  mov     [rsp+arg_8], rdx
0x18000286e  mov     [rsp+arg_0], rcx
0x180002873  push    rsi
0x180002874  push    rdi
0x180002875  push    r13
0x180002877  push    r14
0x180002879  push    r15
0x18000287b  sub     rsp, 40h
0x18000287f  mov     r15, r8
0x180002882  mov     r13, rdx
0x180002885  mov     rdi, rcx
0x180002888  xor     esi, esi
0x18000288a  add     rcx, 98h
0x180002891  call    cs:__imp_IISInitializeCriticalSection
0x180002897  test    eax, eax
0x180002899  jnz     short loc_1800028B4
0x18000289b  call    cs:__imp_GetLastError
0x1800028a1  mov     esi, eax
0x1800028a3  test    eax, eax
0x1800028a5  jle     short loc_1800028B0
0x1800028a7  movzx   esi, ax
0x1800028aa  or      esi, 80070000h
0x1800028b0  mov     [rsp+68h+var_38], esi
0x1800028b4  jmp     short loc_1800028D1
0x1800028b6  mov     esi, 8000FFFFh
0x1800028bb  mov     [rsp+68h+var_38], esi
0x1800028bf  mov     rdi, [rsp+68h+arg_0]
0x1800028c4  mov     r15, [rsp+68h+arg_10]
0x1800028cc  mov     r13, [rsp+68h+arg_8]
0x1800028d1  test    esi, esi
0x1800028d3  js      loc_180002A1A
0x1800028d9  or      dword ptr [rdi+0Ch], 10h
0x1800028dd  mov     [rdi], r15
0x1800028e0  mov     rcx, rdi; this
0x1800028e3  call    ?ReadConfigFromSystem@@YAJPEAVCAppConfig@@H@Z; ReadConfigFromSystem(CAppConfig *,int)
0x1800028e8  mov     esi, eax
0x1800028ea  test    eax, eax
0x1800028ec  js      short loc_180002913
0x1800028ee  lea     r8, [rdi+44h]; struct _GUID *
0x1800028f2  mov     rdx, [rdi+0C8h]; char *
0x1800028f9  call    ?ProgLangIdOfLangName@CScriptManager@@QEAAJPEBDPEAU_GUID@@@Z; CScriptManager::ProgLangIdOfLangName(char const *,_GUID *)
0x1800028fe  not     eax
0x180002900  shr     eax, 1Fh
0x180002903  shl     eax, 2
0x180002906  mov     ecx, [rdi+0Ch]
0x180002909  and     ecx, 0FFFFFFFBh
0x18000290c  or      eax, ecx
0x18000290e  mov     [rdi+0Ch], eax
0x180002911  xor     esi, esi
0x180002913  test    esi, esi
0x180002915  js      loc_180002A0F
0x18000291b  mov     r8, [rdi+0D0h]
0x180002922  test    r8, r8
0x180002925  jz      loc_1800029CE
0x18000292b  mov     [rsp+68h+lpsz], 0
0x180002937  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000293b  inc     rdx; unsigned int
0x18000293e  cmp     byte ptr [r8+rdx], 0
0x180002943  jnz     short loc_18000293B
0x180002945  cmp     byte ptr [r8], 7Bh ; '{'
0x180002949  jnz     short loc_18000297B
0x18000294b  cmp     edx, 2
0x18000294e  jbe     short loc_18000297B
0x180002950  lea     r10d, [rdx-1]
0x180002954  mov     r9d, 1
0x18000295a  cmp     r10d, r9d
0x18000295d  jbe     short loc_180002973
0x18000295f  movsxd  rcx, r9d
0x180002962  mov     al, [rcx+r8]
0x180002966  mov     [rcx+r8-1], al
0x18000296b  inc     r9d
0x18000296e  cmp     r9d, r10d
0x180002971  jb      short loc_18000295F
0x180002973  lea     eax, [rdx-2]
0x180002976  mov     byte ptr [rax+r8], 0
0x18000297b  xor     r9d, r9d; unsigned int
0x18000297e  lea     r8, [rsp+68h+lpsz]; unsigned __int16 **
0x180002986  mov     rcx, [rdi+0D0h]; lpMultiByteStr
0x18000298d  call    ?SysAllocStringFromSz@@YAJPEADKPEAPEAGI@Z; SysAllocStringFromSz(char *,ulong,ushort * *,uint)
0x180002992  mov     r14, [rsp+68h+lpsz]
0x18000299a  test    eax, eax
0x18000299c  js      short loc_1800029BE
0x18000299e  lea     rdx, [rdi+64h]; pclsid
0x1800029a2  mov     rcx, r14; lpsz
0x1800029a5  call    cs:__imp_CLSIDFromString
0x1800029ab  not     eax
0x1800029ad  shr     eax, 1Fh
0x1800029b0  shl     eax, 3
0x1800029b3  mov     edx, [rdi+0Ch]
0x1800029b6  and     edx, 0FFFFFFF7h
0x1800029b9  or      eax, edx
0x1800029bb  mov     [rdi+0Ch], eax
0x1800029be  xor     esi, esi
0x1800029c0  test    r14, r14
0x1800029c3  jz      short loc_1800029CE
0x1800029c5  mov     rcx, r14; bstrString
0x1800029c8  call    cs:__imp_SysFreeString
0x1800029ce  test    esi, esi
0x1800029d0  js      short loc_180002A0F
0x1800029d2  cmp     dword ptr [rdi+80h], 0
0x1800029d9  jz      short loc_180002A0F
0x1800029db  mov     rax, [r13+8]
0x1800029df  lea     r14, [rdi+88h]
0x1800029e6  mov     [rsp+68h+var_48], 0
0x1800029ef  mov     r9, r14
0x1800029f2  mov     r8, [r15+78h]
0x1800029f6  mov     edx, 411h
0x1800029fb  mov     rcx, [rax+8]
0x1800029ff  mov     rax, [rax+0B8h]
0x180002a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0b  test    eax, eax
0x180002a0d  jz      short loc_180002A29
0x180002a0f  or      dword ptr [rdi+0Ch], 1
0x180002a13  mov     dword ptr [rdi+8], 0
0x180002a1a  mov     eax, esi
0x180002a1c  add     rsp, 40h
0x180002a20  pop     r15
0x180002a22  pop     r14
0x180002a24  pop     r13
0x180002a26  pop     rdi
0x180002a27  pop     rsi
0x180002a28  retn
0x180002a29  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180002a30  jmp     short loc_180002A0F
```

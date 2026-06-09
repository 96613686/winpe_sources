# OpenINFEngineW

- ea: `0x180010710`
- end: `0x180010809`
- name: `OpenINFEngineW`
- size: `249`
- prototype: `HRESULT __stdcall(LPCWSTR pszInfFilename, LPCWSTR pszInstallSection, DWORD dwFlags, HINF *phInf, PVOID pvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010670`

## callees

- `0x180003ce0`
- `0x180003e20`
- `0x180004700`
- `0x180004754`
- `0x18000a61c`
- `0x180010710`
- `0x18001b980`

## pseudocode

```c
HRESULT __stdcall OpenINFEngineW(
        LPCWSTR pszInfFilename,
        LPCWSTR pszInstallSection,
        DWORD dwFlags,
        HINF *phInf,
        PVOID pvReserved)
{
  HRESULT v8; // ebx
  unsigned __int16 v10[256]; // [rsp+40h] [rbp-228h] BYREF

  if ( !pszInfFilename || !phInf )
  {
    v8 = -2147024809;
    goto LABEL_12;
  }
  *phInf = 0;
  if ( !(unsigned int)SaveGlobalContext() )
  {
    v8 = -2147024882;
LABEL_12:
    CommonInstallCleanup();
    return v8;
  }
  word_1800257D2 = 1;
  v8 = CommonInstallInit(pszInfFilename, pszInstallSection, v10, 0x100u, 0, 0, 0);
  if ( v8 >= 0 )
  {
    if ( dword_1800257F8 )
    {
      v8 = -2147418113;
    }
    else
    {
      v8 = SetLDIDs(pszInfFilename, v10, 0, 0);
      if ( v8 >= 0 )
      {
        *phInf = InfHandle;
        return v8;
      }
    }
  }
  CommonInstallCleanup();
  RestoreGlobalContext();
  return v8;
}

```

## disassembly

```asm
0x180010710  push    rbx
0x180010712  push    rsi
0x180010713  push    rdi
0x180010714  sub     rsp, 250h
0x18001071b  mov     rax, cs:__security_cookie
0x180010722  xor     rax, rsp
0x180010725  mov     [rsp+268h+var_28], rax
0x18001072d  mov     rdi, r9
0x180010730  mov     rbx, rdx
0x180010733  mov     rsi, rcx
0x180010736  test    rcx, rcx
0x180010739  jz      loc_1800107E2
0x18001073f  test    r9, r9
0x180010742  jz      loc_1800107E2
0x180010748  mov     qword ptr [r9], 0
0x18001074f  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x180010754  test    eax, eax
0x180010756  jnz     short loc_180010762
0x180010758  mov     ebx, 8007000Eh
0x18001075d  jmp     loc_1800107E7
0x180010762  mov     eax, 1
0x180010767  mov     [rsp+268h+var_238], 0; unsigned int
0x18001076f  mov     [rsp+268h+var_240], 0; int
0x180010777  lea     r8, [rsp+268h+var_228]; unsigned __int16 *
0x18001077c  mov     r9d, 100h; unsigned int
0x180010782  mov     cs:word_1800257D2, ax
0x180010789  mov     rdx, rbx; unsigned __int16 *
0x18001078c  mov     [rsp+268h+var_248], 0; unsigned __int16 *
0x180010795  mov     rcx, rsi; unsigned __int16 *
0x180010798  call    ?CommonInstallInit@@YAJPEBG0PEAGK0HK@Z; CommonInstallInit(ushort const *,ushort const *,ushort *,ulong,ushort const *,int,ulong)
0x18001079d  mov     ebx, eax
0x18001079f  test    eax, eax
0x1800107a1  js      short loc_1800107B1
0x1800107a3  cmp     cs:dword_1800257F8, 0
0x1800107aa  jz      short loc_1800107BD
0x1800107ac  mov     ebx, 8000FFFFh
0x1800107b1  call    ?CommonInstallCleanup@@YAXXZ; CommonInstallCleanup(void)
0x1800107b6  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x1800107bb  jmp     short loc_1800107EC
0x1800107bd  xor     r9d, r9d; unsigned __int16 *
0x1800107c0  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x1800107c5  xor     r8d, r8d; unsigned int
0x1800107c8  mov     rcx, rsi; unsigned __int16 *
0x1800107cb  call    ?SetLDIDs@@YAJPEBG0K0@Z; SetLDIDs(ushort const *,ushort const *,ulong,ushort const *)
0x1800107d0  mov     ebx, eax
0x1800107d2  test    eax, eax
0x1800107d4  js      short loc_1800107B1
0x1800107d6  mov     rax, cs:InfHandle
0x1800107dd  mov     [rdi], rax
0x1800107e0  jmp     short loc_1800107EC
0x1800107e2  mov     ebx, 80070057h
0x1800107e7  call    ?CommonInstallCleanup@@YAXXZ; CommonInstallCleanup(void)
0x1800107ec  mov     eax, ebx
0x1800107ee  mov     rcx, [rsp+268h+var_28]
0x1800107f6  xor     rcx, rsp; StackCookie
0x1800107f9  call    __security_check_cookie
0x1800107fe  add     rsp, 250h
0x180010805  pop     rdi
0x180010806  pop     rsi
0x180010807  pop     rbx
0x180010808  retn
```

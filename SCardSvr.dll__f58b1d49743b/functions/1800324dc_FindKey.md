# FindKey

- ea: `0x1800324dc`
- end: `0x180032615`
- name: `FindKey`
- size: `313`
- prototype: `void __fastcall(ulong, const WCHAR *, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800174e8`

## callees

- `0x180017664`
- `0x1800176a8`
- `0x18001a328`
- `0x1800324dc`
- `0x18003261b`

## string_xrefs

- `0x18003251f`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall FindKey(ulong a1, const WCHAR *a2, DWORD *a3)
{
  __int64 i; // rdi
  const WCHAR *v6; // rsi
  unsigned int j; // ebx
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-48h]
  HKEY phkResult[5]; // [rsp+40h] [rbp-38h] BYREF
  int v10; // [rsp+68h] [rbp-10h]
  ulong pExceptionObject; // [rsp+B0h] [rbp+38h] BYREF

  pExceptionObject = a1;
  phkResult[2] = (HKEY)&CBuffer::`vftable';
  phkResult[3] = 0;
  phkResult[4] = 0;
  phkResult[0] = 0;
  v10 = 1010;
  lpSubKey[0] = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers";
  lpSubKey[1] = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 2 )
    {
      pExceptionObject = 2;
      throw &pExceptionObject;
    }
    v6 = lpSubKey[i];
    if ( v6 )
      break;
LABEL_10:
    ;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= 2 )
      goto LABEL_10;
    if ( LODWORD(qword_18003C880[2 * j]) >= 2 )
    {
      CRegistry::Open((DWORD *)phkResult, (HKEY)qword_18003C880[2 * j + 1], v6, 0x20019u, 0xFFFFFFE0);
      if ( !(unsigned int)CRegistry::Status((CRegistry *)phkResult, 1) )
      {
        CRegistry::Status((CRegistry *)phkResult, 0);
        CRegistry::Open(a3, phkResult[0], a2, 0x20019u, 0xFFFFFFE0);
        if ( !(unsigned int)CRegistry::Status((CRegistry *)a3, 1) )
          break;
      }
    }
  }
  CRegistry::~CRegistry((CRegistry *)phkResult);
}

```

## disassembly

```asm
0x1800324dc  mov     [rsp-30h+pExceptionObject], ecx
0x1800324e0  push    rbp
0x1800324e1  push    rbx
0x1800324e2  push    rsi
0x1800324e3  push    rdi
0x1800324e4  push    r14
0x1800324e6  push    r15
0x1800324e8  mov     rbp, rsp
0x1800324eb  sub     rsp, 78h
0x1800324ef  mov     r14, r8
0x1800324f2  mov     r15, rdx
0x1800324f5  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800324fc  mov     [rbp+var_28], rax
0x180032500  mov     [rbp+var_20], 0
0x180032508  mov     [rbp+var_18], 0
0x180032510  mov     [rbp+phkResult], 0
0x180032518  mov     [rbp+var_10], 3F2h
0x18003251f  lea     rax, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180032526  mov     [rbp+lpSubKey], rax
0x18003252a  mov     [rbp+var_40], 0
0x180032532  xor     edi, edi
0x180032534  lea     rcx, qword_18003C880
0x18003253b  cmp     edi, 2
0x18003253e  jnb     loc_1800325FD
0x180032544  mov     rsi, [rbp+rdi*8+lpSubKey]
0x180032549  test    rsi, rsi
0x18003254c  jz      loc_1800325E0
0x180032552  xor     ebx, ebx
0x180032554  cmp     ebx, 2
0x180032557  jnb     loc_1800325E0
0x18003255d  mov     edx, ebx
0x18003255f  add     rdx, rdx
0x180032562  cmp     dword ptr [rcx+rdx*8], 2
0x180032566  jb      short loc_1800325D9
0x180032568  mov     [rsp+78h+dwOptions], 0FFFFFFE0h; dwOptions
0x180032570  mov     r9d, 20019h; samDesired
0x180032576  mov     r8, rsi; lpSubKey
0x180032579  mov     rdx, [rcx+rdx*8+8]; hKey
0x18003257e  lea     rcx, [rbp+phkResult]; phkResult
0x180032582  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x180032587  mov     edx, 1; int
0x18003258c  lea     rcx, [rbp+phkResult]; this
0x180032590  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x180032595  test    eax, eax
0x180032597  jnz     short loc_1800325D2
0x180032599  xor     edx, edx; int
0x18003259b  lea     rcx, [rbp+phkResult]; this
0x18003259f  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x1800325a4  mov     [rsp+78h+dwOptions], 0FFFFFFE0h; dwOptions
0x1800325ac  mov     r9d, 20019h; samDesired
0x1800325b2  mov     r8, r15; lpSubKey
0x1800325b5  mov     rdx, [rbp+phkResult]; hKey
0x1800325b9  mov     rcx, r14; phkResult
0x1800325bc  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x1800325c1  mov     edx, 1; int
0x1800325c6  mov     rcx, r14; this
0x1800325c9  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x1800325ce  test    eax, eax
0x1800325d0  jz      short loc_1800325E7
0x1800325d2  lea     rcx, qword_18003C880
0x1800325d9  inc     ebx
0x1800325db  jmp     loc_180032554
0x1800325e0  inc     edi
0x1800325e2  jmp     loc_18003253B
0x1800325e7  lea     rcx, [rbp+phkResult]; this
0x1800325eb  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800325f0  add     rsp, 78h
0x1800325f4  pop     r15
0x1800325f6  pop     r14
0x1800325f8  pop     rdi
0x1800325f9  pop     rsi
0x1800325fa  pop     rbx
0x1800325fb  pop     rbp
0x1800325fc  retn
0x1800325fd  mov     [rbp+pExceptionObject], 2
0x180032604  lea     rdx, _TI1K; pThrowInfo
0x18003260b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003260f  call    _CxxThrowException_0
```

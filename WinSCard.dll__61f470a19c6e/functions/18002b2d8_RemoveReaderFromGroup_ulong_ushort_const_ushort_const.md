# RemoveReaderFromGroup(ulong,ushort const *,ushort const *)

- ea: `0x18002b2d8`
- end: `0x18002b48a`
- name: `?RemoveReaderFromGroup@@YAXKPEBG0@Z`
- size: `434`
- prototype: `void(unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026d80`
- `0x180028790`

## callees

- `0x180002180`
- `0x180002220`
- `0x1800040d0`
- `0x18000e3d0`
- `0x180010400`
- `0x180013c90`
- `0x180015ac0`
- `0x18002a02c`
- `0x18002a118`
- `0x18002a65c`
- `0x18002b2d8`
- `0x18002ef20`

## string_xrefs

- `0x18002b39a`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
void __fastcall RemoveReaderFromGroup(int a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v6; // ecx
  unsigned int *v7; // r9
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rdi
  unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  ulong v12; // r9d
  const int *v13; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int16 *v14; // [rsp+38h] [rbp-41h]
  __int64 v15; // [rsp+40h] [rbp-39h]
  const int *v16; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v17; // [rsp+50h] [rbp-29h]
  __int64 v18; // [rsp+58h] [rbp-21h]
  HKEY hKey[5]; // [rsp+60h] [rbp-19h] BYREF
  int v20; // [rsp+88h] [rbp+Fh]
  _DWORD phkResult[12]; // [rsp+90h] [rbp+17h] BYREF
  unsigned __int16 *pExceptionObject; // [rsp+F0h] [rbp+77h] BYREF

  v16 = &CBuffer::`vftable';
  v17 = 0;
  v18 = 0;
  v13 = &CBuffer::`vftable';
  v14 = 0;
  v15 = 0;
  hKey[2] = (HKEY)&CBuffer::`vftable';
  hKey[3] = 0;
  hKey[4] = 0;
  hKey[0] = 0;
  v20 = 1010;
  if ( !*a3 )
  {
    LODWORD(pExceptionObject) = -2146435055;
    throw (ulong *)&pExceptionObject;
  }
  v6 = 0;
  while ( dword_180039DB0[4 * v6] != a1 )
  {
    if ( (unsigned int)++v6 >= 2 )
    {
      LODWORD(pExceptionObject) = -2146435055;
      throw (ulong *)&pExceptionObject;
    }
  }
  CRegistry::Open(
    hKey,
    *(HKEY *)&dword_180039DB0[4 * v6 + 2],
    L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers",
    0x20019u,
    0xFFFFFFE0);
  CRegistry::Status((CRegistry *)hKey, 0);
  CRegistry::CRegistry(phkResult, hKey[0], a2, 0x2001Bu, 0xFFFFFFE0);
  MStrAdd((struct CBuffer *)&v13, a3);
  pExceptionObject = 0;
  CRegistry::GetValue((CRegistry *)phkResult, L"Groups", &pExceptionObject, v7);
  v8 = MStringCount(pExceptionObject);
  v9 = (unsigned __int16 *)&WideCharStr;
  v10 = (unsigned __int16 *)&WideCharStr;
  if ( HIDWORD(v15) )
    v10 = v14;
  if ( v8 != MStringRemove(pExceptionObject, v10, (struct CBuffer *)&v16) )
  {
    if ( HIDWORD(v18) )
      v9 = v17;
    CRegistry::SetMultiStringValue((CRegistry *)phkResult, v11, v9, v12);
  }
  CRegistry::~CRegistry((CRegistry *)phkResult);
  CRegistry::~CRegistry((CRegistry *)hKey);
  v13 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v13);
  v16 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v16);
}

```

## disassembly

```asm
0x18002b2d8  mov     [rsp-8+arg_0], rbx
0x18002b2dd  mov     [rsp-8+arg_8], rdi
0x18002b2e2  push    rbp
0x18002b2e3  push    r14
0x18002b2e5  push    r15
0x18002b2e7  lea     rbp, [rsp-47h]
0x18002b2ec  sub     rsp, 0C0h
0x18002b2f3  mov     rbx, r8
0x18002b2f6  mov     rdi, rdx
0x18002b2f9  mov     r8d, ecx
0x18002b2fc  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002b303  mov     [rbp+57h+var_88], r15
0x18002b307  xor     r14d, r14d
0x18002b30a  mov     [rbp+57h+var_80], r14
0x18002b30e  mov     [rbp+57h+var_78], r14
0x18002b312  mov     [rbp+57h+var_A0], r15
0x18002b316  mov     [rbp+57h+var_98], r14
0x18002b31a  mov     [rbp+57h+var_90], r14
0x18002b31e  mov     [rbp+57h+var_60], r15
0x18002b322  mov     [rbp+57h+var_58], r14
0x18002b326  mov     [rbp+57h+var_50], r14
0x18002b32a  mov     [rbp+57h+hKey], r14
0x18002b32e  mov     [rbp+57h+var_48], 3F2h
0x18002b335  cmp     r14w, [rbx]
0x18002b339  jnz     short loc_18002B353
0x18002b33b  mov     dword ptr [rbp+57h+pExceptionObject], 80100011h
0x18002b342  lea     rdx, _TI1K; pThrowInfo
0x18002b349  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b34d  call    _CxxThrowException_0
0x18002b353  mov     ecx, r14d
0x18002b356  lea     r10, dword_180039DB0
0x18002b35d  mov     eax, ecx
0x18002b35f  add     rax, rax
0x18002b362  cmp     [r10+rax*8], r8d
0x18002b366  jz      short loc_18002B387
0x18002b368  inc     ecx
0x18002b36a  cmp     ecx, 2
0x18002b36d  jb      short loc_18002B35D
0x18002b36f  mov     dword ptr [rbp+57h+pExceptionObject], 80100011h
0x18002b376  lea     rdx, _TI1K; pThrowInfo
0x18002b37d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b381  call    _CxxThrowException_0
0x18002b387  mov     edx, ecx
0x18002b389  add     rdx, rdx
0x18002b38c  mov     [rsp+0D0h+dwOptions], 0FFFFFFE0h; dwOptions
0x18002b394  mov     r9d, 20019h; samDesired
0x18002b39a  lea     r8, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002b3a1  mov     rdx, [r10+rdx*8+8]; hKey
0x18002b3a6  lea     rcx, [rbp+57h+hKey]; phkResult
0x18002b3aa  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002b3af  xor     edx, edx; int
0x18002b3b1  lea     rcx, [rbp+57h+hKey]; this
0x18002b3b5  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x18002b3ba  mov     [rsp+0D0h+dwOptions], 0FFFFFFE0h; dwOptions
0x18002b3c2  mov     r9d, 2001Bh; samDesired
0x18002b3c8  mov     r8, rdi; lpSubKey
0x18002b3cb  mov     rdx, [rbp+57h+hKey]; hKey
0x18002b3cf  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18002b3d3  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::CRegistry(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002b3d8  nop
0x18002b3d9  mov     rdx, rbx; unsigned __int16 *
0x18002b3dc  lea     rcx, [rbp+57h+var_A0]; struct CBuffer *
0x18002b3e0  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18002b3e5  mov     [rbp+57h+pExceptionObject], r14
0x18002b3e9  lea     r8, [rbp+57h+pExceptionObject]; unsigned __int16 **
0x18002b3ed  lea     rdx, aGroups_1; "Groups"
0x18002b3f4  lea     rcx, [rbp+57h+phkResult]; this
0x18002b3f8  call    ?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z; CRegistry::GetValue(ushort const *,ushort * *,ulong *)
0x18002b3fd  mov     rcx, [rbp+57h+pExceptionObject]; unsigned __int16 *
0x18002b401  call    ?MStringCount@@YAKPEBG@Z; MStringCount(ushort const *)
0x18002b406  mov     ebx, eax
0x18002b408  lea     rdi, WideCharStr
0x18002b40f  mov     rdx, rdi
0x18002b412  cmp     dword ptr [rbp+57h+var_90+4], r14d
0x18002b416  cmova   rdx, [rbp+57h+var_98]; unsigned __int16 *
0x18002b41b  lea     r8, [rbp+57h+var_88]; struct CBuffer *
0x18002b41f  mov     rcx, [rbp+57h+pExceptionObject]; unsigned __int16 *
0x18002b423  call    ?MStringRemove@@YAKPEBG0AEAVCBuffer@@@Z; MStringRemove(ushort const *,ushort const *,CBuffer &)
0x18002b428  cmp     ebx, eax
0x18002b42a  jz      short loc_18002B442
0x18002b42c  cmp     dword ptr [rbp+57h+var_78+4], r14d
0x18002b430  cmova   rdi, [rbp+57h+var_80]
0x18002b435  mov     r8, rdi; unsigned __int16 *
0x18002b438  lea     rcx, [rbp+57h+phkResult]; this
0x18002b43c  call    ?SetMultiStringValue@CRegistry@@QEBAXPEBG0K@Z; CRegistry::SetMultiStringValue(ushort const *,ushort const *,ulong)
0x18002b441  nop
0x18002b442  lea     rcx, [rbp+57h+phkResult]; this
0x18002b446  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002b44b  nop
0x18002b44c  lea     rcx, [rbp+57h+hKey]; this
0x18002b450  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002b455  nop
0x18002b456  mov     [rbp+57h+var_A0], r15
0x18002b45a  lea     rcx, [rbp+57h+var_A0]; this
0x18002b45e  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002b463  nop
0x18002b464  mov     [rbp+57h+var_88], r15
0x18002b468  lea     rcx, [rbp+57h+var_88]; this
0x18002b46c  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002b471  lea     r11, [rsp+0D0h+var_10]
0x18002b479  mov     rbx, [r11+20h]
0x18002b47d  mov     rdi, [r11+28h]
0x18002b481  mov     rsp, r11
0x18002b484  pop     r15
0x18002b486  pop     r14
0x18002b488  pop     rbp
0x18002b489  retn
```

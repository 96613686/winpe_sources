# DllGetClassObject

- ea: `0x18000ab60`
- end: `0x18000aca3`
- name: `DllGetClassObject`
- size: `323`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ab60`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac52`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // r14d
  __int64 *i; // rax
  __int64 v7; // rbx
  _DWORD *v8; // r9
  __int64 (__fastcall ***v9)(_QWORD, const IID *const, LPVOID *); // rcx

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  v5 = 0;
  *ppv = 0;
  for ( i = (__int64 *)qword_180026AD0; (unsigned __int64)i < qword_180026AD8; ++i )
  {
    v7 = *i;
    if ( *i )
    {
      if ( *(_QWORD *)(v7 + 16) )
      {
        v8 = *(_DWORD **)v7;
        if ( rclsid->Data1 == **(_DWORD **)v7
          && *(_DWORD *)&rclsid->Data2 == v8[1]
          && *(_DWORD *)rclsid->Data4 == v8[2]
          && *(_DWORD *)&rclsid->Data4[4] == v8[3] )
        {
          if ( !*(_QWORD *)(v7 + 32) )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)&CriticalSection);
            if ( !*(_QWORD *)(v7 + 32) )
              v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection((LPCRITICAL_SECTION)&CriticalSection);
          }
          v9 = *(__int64 (__fastcall ****)(_QWORD, const IID *const, LPVOID *))(v7 + 32);
          if ( v9 )
            v5 = (**v9)(v9, riid, ppv);
          break;
        }
      }
    }
  }
  if ( !*ppv && !v5 )
    return -2147221231;
  return v5;
}

```

## disassembly

```asm
0x18000ab60  mov     [rsp+arg_18], rbp
0x18000ab65  push    rdi
0x18000ab66  sub     rsp, 20h
0x18000ab6a  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000ab71  mov     rdi, r8
0x18000ab74  mov     r8, rcx
0x18000ab77  mov     rbp, rdx
0x18000ab7a  jz      loc_18000AC3B
0x18000ab80  test    rdi, rdi
0x18000ab83  jz      loc_18000AC8B
0x18000ab89  mov     [rsp+28h+arg_10], r14
0x18000ab8e  xor     r14d, r14d
0x18000ab91  mov     qword ptr [rdi], 0
0x18000ab98  mov     rax, cs:qword_180026AD0
0x18000ab9f  mov     rdx, cs:qword_180026AD8
0x18000aba6  mov     [rsp+28h+arg_0], rbx
0x18000abab  cmp     rax, rdx
0x18000abae  jnb     short loc_18000AC14
0x18000abb0  mov     rbx, [rax]
0x18000abb3  test    rbx, rbx
0x18000abb6  jz      short loc_18000AC32
0x18000abb8  cmp     [rbx+10h], r14
0x18000abbc  jz      short loc_18000AC32
0x18000abbe  mov     r9, [rbx]
0x18000abc1  mov     ecx, [r9]
0x18000abc4  cmp     [r8], ecx
0x18000abc7  jnz     short loc_18000AC32
0x18000abc9  mov     ecx, [r9+4]
0x18000abcd  cmp     [r8+4], ecx
0x18000abd1  jnz     short loc_18000AC32
0x18000abd3  mov     ecx, [r9+8]
0x18000abd7  cmp     [r8+8], ecx
0x18000abdb  jnz     short loc_18000AC32
0x18000abdd  mov     ecx, [r9+0Ch]
0x18000abe1  cmp     [r8+0Ch], ecx
0x18000abe5  jnz     short loc_18000AC32
0x18000abe7  mov     [rsp+28h+arg_8], rsi
0x18000abec  cmp     [rbx+20h], r14
0x18000abf0  jz      short loc_18000AC4B
0x18000abf2  mov     rcx, [rbx+20h]
0x18000abf6  mov     rsi, [rsp+28h+arg_8]
0x18000abfb  test    rcx, rcx
0x18000abfe  jz      short loc_18000AC14
0x18000ac00  mov     rax, [rcx]
0x18000ac03  mov     r8, rdi
0x18000ac06  mov     rdx, rbp
0x18000ac09  mov     rax, [rax]
0x18000ac0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac11  mov     r14d, eax
0x18000ac14  cmp     qword ptr [rdi], 0
0x18000ac18  mov     rbx, [rsp+28h+arg_0]
0x18000ac1d  jz      short loc_18000AC92
0x18000ac1f  mov     eax, r14d
0x18000ac22  mov     r14, [rsp+28h+arg_10]
0x18000ac27  mov     rbp, [rsp+28h+arg_18]
0x18000ac2c  add     rsp, 20h
0x18000ac30  pop     rdi
0x18000ac31  retn
0x18000ac32  add     rax, 8
0x18000ac36  jmp     loc_18000ABAB
0x18000ac3b  mov     rbp, [rsp+28h+arg_18]
0x18000ac40  mov     eax, 8000FFFFh
0x18000ac45  add     rsp, 20h
0x18000ac49  pop     rdi
0x18000ac4a  retn
0x18000ac4b  lea     rcx, CriticalSection; lpCriticalSection
0x18000ac52  call    cs:__imp_EnterCriticalSection
0x18000ac58  cmp     [rbx+20h], r14
0x18000ac5c  jnz     short loc_18000AC79
0x18000ac5e  mov     rcx, [rbx+18h]
0x18000ac62  lea     r8, [rbx+20h]
0x18000ac66  mov     rax, [rbx+10h]
0x18000ac6a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000ac71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac76  mov     r14d, eax
0x18000ac79  lea     rcx, CriticalSection; lpCriticalSection
0x18000ac80  call    cs:__imp_LeaveCriticalSection
0x18000ac86  jmp     loc_18000ABF2
0x18000ac8b  mov     eax, 80004003h
0x18000ac90  jmp     short loc_18000AC27
0x18000ac92  test    r14d, r14d
0x18000ac95  mov     eax, 80040111h
0x18000ac9a  cmovz   r14d, eax
0x18000ac9e  jmp     loc_18000AC1F
```

# DpspUpdateEnabledScenarioCount

- ea: `0x180008858`
- end: `0x180008989`
- name: `DpspUpdateEnabledScenarioCount`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000866c`
- `0x1800166f4`

## callees

- `0x180008858`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008968`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008968`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800088e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800088e9`

## string_xrefs

- `0x180008882`: `DpspUpdateEnabledScenarioCount`

## pseudocode

```c
__int64 __fastcall DpspUpdateEnabledScenarioCount(__int64 a1, int a2)
{
  unsigned int v3; // ebp
  unsigned int v4; // eax
  int v5; // r14d
  __int64 i; // rsi
  __int64 v7; // rbx
  int v8; // edx
  BOOL v9; // r8d
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  BOOL v13; // eax

  if ( a1 )
  {
    v3 = 0;
    v4 = *(_DWORD *)(a1 + 40) - 1;
    if ( (unsigned int)(a2 - 1) <= 1 )
    {
      if ( v4 <= 1 )
        return v3;
      v5 = 2;
    }
    else
    {
      if ( v4 > 1 )
        return v3;
      v5 = 1;
    }
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 24); i = (unsigned int)(i + 1) )
    {
      v7 = *(_QWORD *)(a1 + 8 * i + 96);
      if ( v7 )
        EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 64));
      v8 = *(_DWORD *)(v7 + 152) & 2;
      v9 = !v8 || !*(_DWORD *)(v7 + 156);
      v10 = *(_DWORD *)(v7 + 156);
      v11 = v10 - 1;
      v12 = v10 + 1;
      if ( v5 != 1 )
        v12 = v11;
      *(_DWORD *)(v7 + 156) = v12;
      v13 = !v8 || !v12;
      if ( v9 )
      {
        if ( !v13 && (unsigned int)(*(_DWORD *)(v7 + 24) - 2) <= 1 )
          _InterlockedDecrement(&g_lUnloadableDMCount);
      }
      else if ( v13 && (unsigned int)(*(_DWORD *)(v7 + 24) - 2) <= 1 )
      {
        _InterlockedAdd(&g_lUnloadableDMCount, 1u);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 64));
    }
  }
  else
  {
    v3 = -2147024809;
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsgp.cpp",
      (__int64)L"DpspUpdateEnabledScenarioCount",
      981,
      (const wchar_t *)L"Error = %d",
      87);
  }
  return v3;
}

```

## disassembly

```asm
0x180008858  push    rbx
0x18000885a  push    rbp
0x18000885b  push    rsi
0x18000885c  push    rdi
0x18000885d  push    r14
0x18000885f  push    r15
0x180008861  sub     rsp, 38h
0x180008865  mov     rdi, rcx
0x180008868  test    rcx, rcx
0x18000886b  jnz     short loc_18000889F
0x18000886d  lea     r9, aErrorD; "Error = %d"
0x180008874  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000887c  mov     r8d, 3D5h; int
0x180008882  lea     rdx, aDpspupdateenab; "DpspUpdateEnabledScenarioCount"
0x180008889  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008890  mov     ebp, 80070057h
0x180008895  call    WdipTraceError
0x18000889a  jmp     loc_18000897A
0x18000889f  mov     ecx, [rcx+28h]
0x1800088a2  lea     eax, [rdx-1]
0x1800088a5  xor     ebp, ebp
0x1800088a7  lea     r15d, [rbp+1]
0x1800088ab  cmp     eax, r15d
0x1800088ae  lea     eax, [rcx-1]
0x1800088b1  jbe     short loc_1800088C1
0x1800088b3  cmp     eax, r15d
0x1800088b6  ja      loc_18000897A
0x1800088bc  mov     r14d, r15d
0x1800088bf  jmp     short loc_1800088D0
0x1800088c1  cmp     eax, r15d
0x1800088c4  jbe     loc_18000897A
0x1800088ca  mov     r14d, 2
0x1800088d0  xor     esi, esi
0x1800088d2  cmp     [rdi+18h], esi
0x1800088d5  jbe     loc_18000897A
0x1800088db  mov     rbx, [rdi+rsi*8+60h]
0x1800088e0  test    rbx, rbx
0x1800088e3  jz      short loc_1800088EF
0x1800088e5  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800088e9  call    cs:__imp_EnterCriticalSection
0x1800088ef  mov     edx, [rbx+98h]
0x1800088f5  and     edx, 2
0x1800088f8  jz      short loc_180008907
0x1800088fa  cmp     [rbx+9Ch], ebp
0x180008900  jz      short loc_180008907
0x180008902  xor     r8d, r8d
0x180008905  jmp     short loc_18000890A
0x180008907  mov     r8d, r15d
0x18000890a  mov     eax, [rbx+9Ch]
0x180008910  lea     ecx, [rax-1]
0x180008913  inc     eax
0x180008915  cmp     r14d, r15d
0x180008918  cmovnz  eax, ecx
0x18000891b  mov     [rbx+9Ch], eax
0x180008921  test    edx, edx
0x180008923  jz      short loc_18000892D
0x180008925  test    eax, eax
0x180008927  jz      short loc_18000892D
0x180008929  xor     eax, eax
0x18000892b  jmp     short loc_180008930
0x18000892d  mov     eax, r15d
0x180008930  test    r8d, r8d
0x180008933  jz      short loc_18000894D
0x180008935  test    eax, eax
0x180008937  jnz     short loc_180008964
0x180008939  mov     eax, [rbx+18h]
0x18000893c  sub     eax, 2
0x18000893f  cmp     eax, r15d
0x180008942  ja      short loc_180008964
0x180008944  lock dec cs:g_lUnloadableDMCount
0x18000894b  jmp     short loc_180008964
0x18000894d  test    eax, eax
0x18000894f  jz      short loc_180008964
0x180008951  mov     ecx, [rbx+18h]
0x180008954  sub     ecx, 2
0x180008957  cmp     ecx, r15d
0x18000895a  ja      short loc_180008964
0x18000895c  lock add cs:g_lUnloadableDMCount, r15d
0x180008964  lea     rcx, [rbx+40h]; lpCriticalSection
0x180008968  call    cs:__imp_LeaveCriticalSection
0x18000896e  add     esi, r15d
0x180008971  cmp     esi, [rdi+18h]
0x180008974  jb      loc_1800088DB
0x18000897a  mov     eax, ebp
0x18000897c  add     rsp, 38h
0x180008980  pop     r15
0x180008982  pop     r14
0x180008984  pop     rdi
0x180008985  pop     rsi
0x180008986  pop     rbp
0x180008987  pop     rbx
0x180008988  retn
```

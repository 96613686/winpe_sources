# DllGetClassObject

- ea: `0x180022544`
- end: `0x18002265e`
- name: `DllGetClassObject`
- size: `282`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180022544`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180022613`
- `KERNEL32!LeaveCriticalSection` at `0x180022613`
- `KERNEL32!EnterCriticalSection` at `0x1800225ec`
- `KERNEL32!EnterCriticalSection` at `0x1800225ec`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  _QWORD **v7; // rcx
  __int64 v8; // r9
  _QWORD *v9; // rsi
  _DWORD *v10; // rdx

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  if ( !dword_1800A3730 )
    return -2147418113;
  v7 = (_QWORD **)qword_1800A3740;
  v8 = qword_1800A3748;
  v6 = 0;
  while ( 1 )
  {
    if ( (unsigned __int64)v7 >= qword_1800A3748 )
      return -2147221231;
    v9 = *v7;
    if ( *v7 )
    {
      if ( v9[2] )
      {
        v10 = (_DWORD *)*v9;
        if ( rclsid->Data1 == *(_DWORD *)*v9
          && *(_DWORD *)&rclsid->Data2 == v10[1]
          && *(_DWORD *)rclsid->Data4 == v10[2]
          && *(_DWORD *)&rclsid->Data4[4] == v10[3] )
        {
          break;
        }
      }
    }
    ++v7;
  }
  if ( !v9[4] )
  {
    EnterCriticalSection(&CriticalSection);
    if ( !v9[4] )
      v6 = ((__int64 (__fastcall *)(_QWORD, __int64 *, _QWORD *))v9[2])(v9[3], &qword_180006708, v9 + 4);
    LeaveCriticalSection(&CriticalSection);
  }
  if ( v9[4] )
    v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *, __int64))v9[4])(v9[4], riid, ppv, v8);
  if ( !*ppv && !v6 )
    return -2147221231;
  return v6;
}

```

## disassembly

```asm
0x180022544  mov     rax, rsp
0x180022547  mov     [rax+8], rbx
0x18002254b  mov     [rax+10h], rbp
0x18002254f  mov     [rax+18h], rsi
0x180022553  mov     [rax+20h], rdi
0x180022557  push    r12
0x180022559  sub     rsp, 20h
0x18002255d  mov     rbp, r8
0x180022560  mov     r12, rdx
0x180022563  mov     r8, rcx
0x180022566  test    rbp, rbp
0x180022569  jnz     short loc_180022575
0x18002256b  mov     ebx, 80004003h
0x180022570  jmp     loc_180022641
0x180022575  and     qword ptr [rbp+0], 0
0x18002257a  cmp     cs:dword_1800A3730, 0
0x180022581  jnz     short loc_18002258D
0x180022583  mov     ebx, 8000FFFFh
0x180022588  jmp     loc_180022641
0x18002258d  mov     rcx, cs:qword_1800A3740
0x180022594  mov     r9, cs:qword_1800A3748
0x18002259b  xor     ebx, ebx
0x18002259d  cmp     rcx, r9
0x1800225a0  jnb     loc_18002263C
0x1800225a6  mov     rsi, [rcx]
0x1800225a9  test    rsi, rsi
0x1800225ac  jz      short loc_1800225D9
0x1800225ae  cmp     [rsi+10h], rbx
0x1800225b2  jz      short loc_1800225D9
0x1800225b4  mov     rdx, [rsi]
0x1800225b7  mov     eax, [rdx]
0x1800225b9  cmp     [r8], eax
0x1800225bc  jnz     short loc_1800225D9
0x1800225be  mov     eax, [rdx+4]
0x1800225c1  cmp     [r8+4], eax
0x1800225c5  jnz     short loc_1800225D9
0x1800225c7  mov     eax, [rdx+8]
0x1800225ca  cmp     [r8+8], eax
0x1800225ce  jnz     short loc_1800225D9
0x1800225d0  mov     eax, [rdx+0Ch]
0x1800225d3  cmp     [r8+0Ch], eax
0x1800225d7  jz      short loc_1800225DF
0x1800225d9  add     rcx, 8
0x1800225dd  jmp     short loc_18002259D
0x1800225df  cmp     [rsi+20h], rbx
0x1800225e3  jnz     short loc_180022619
0x1800225e5  lea     rcx, CriticalSection; lpCriticalSection
0x1800225ec  call    cs:EnterCriticalSection
0x1800225f2  cmp     [rsi+20h], rbx
0x1800225f6  jnz     short loc_18002260C
0x1800225f8  mov     rcx, [rsi+18h]
0x1800225fc  lea     r8, [rsi+20h]
0x180022600  lea     rdx, qword_180006708
0x180022607  call    qword ptr [rsi+10h]
0x18002260a  mov     ebx, eax
0x18002260c  lea     rcx, CriticalSection; lpCriticalSection
0x180022613  call    cs:LeaveCriticalSection
0x180022619  cmp     qword ptr [rsi+20h], 0
0x18002261e  jz      short loc_180022631
0x180022620  mov     rcx, [rsi+20h]
0x180022624  mov     r8, rbp
0x180022627  mov     rdx, r12
0x18002262a  mov     rax, [rcx]
0x18002262d  call    qword ptr [rax]
0x18002262f  mov     ebx, eax
0x180022631  cmp     qword ptr [rbp+0], 0
0x180022636  jnz     short loc_180022641
0x180022638  test    ebx, ebx
0x18002263a  jnz     short loc_180022641
0x18002263c  mov     ebx, 80040111h
0x180022641  mov     rbp, [rsp+28h+arg_8]
0x180022646  mov     rsi, [rsp+28h+arg_10]
0x18002264b  mov     rdi, [rsp+28h+arg_18]
0x180022650  mov     eax, ebx
0x180022652  mov     rbx, [rsp+28h+arg_0]
0x180022657  add     rsp, 20h
0x18002265b  pop     r12
0x18002265d  retn
```

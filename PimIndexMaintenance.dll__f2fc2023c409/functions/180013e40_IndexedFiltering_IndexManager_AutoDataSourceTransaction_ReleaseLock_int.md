# IndexedFiltering::IndexManager::AutoDataSourceTransaction::ReleaseLock(int)

- ea: `0x180013e40`
- end: `0x180013f0e`
- name: `?ReleaseLock@AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAAJH@Z`
- size: `206`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexManager::AutoDataSourceTransaction *__hidden this, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180012c9c`
- `0x180014020`
- `0x1800144c0`
- `0x1800148a8`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180013e40`
- `0x180022010`

## string_xrefs

- `0x180013ead`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\IndexManager.h`
- `0x180013edc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\IndexManager.h`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::AutoDataSourceTransaction::ReleaseLock(
        IndexedFiltering::IndexManager::AutoDataSourceTransaction *this,
        unsigned int a2)
{
  _QWORD **v4; // rcx
  int v5; // edi
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v9; // rcx
  unsigned __int16 v10; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 5) )
  {
    if ( a2 )
    {
      if ( *((_DWORD *)this + 4) )
      {
        v4 = *(_QWORD ***)this;
        v10 = 0;
        if ( ((int (__fastcall *)(_QWORD **, unsigned __int16 *))(*v4)[8])(v4, &v10) >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(***((_QWORD ***)this + 1) + 96LL))(
                 **((_QWORD **)this + 1),
                 v10);
          if ( v5 < 0 )
          {
            v6 = 276;
            v7 = 0;
LABEL_7:
            Log_HREvent(
              (unsigned int)v5,
              v7,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\IndexManager.h",
              v6);
            return (unsigned int)v5;
          }
        }
      }
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, a2);
    if ( v5 < 0 )
    {
      Log_AssertionEvent(
        v9,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\IndexManager.h",
        281);
      v6 = 282;
      v7 = 1;
      goto LABEL_7;
    }
    *((_DWORD *)this + 5) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180013e40  mov     [rsp+arg_8], rbx
0x180013e45  mov     [rsp+arg_10], rsi
0x180013e4a  push    rdi
0x180013e4b  sub     rsp, 30h
0x180013e4f  cmp     dword ptr [rcx+14h], 0
0x180013e53  mov     esi, edx
0x180013e55  mov     rbx, rcx
0x180013e58  jz      loc_180013EFC
0x180013e5e  test    edx, edx
0x180013e60  jz      short loc_180013EBF
0x180013e62  cmp     dword ptr [rcx+10h], 0
0x180013e66  jbe     short loc_180013EBF
0x180013e68  mov     rcx, [rcx]
0x180013e6b  lea     rdx, [rsp+38h+arg_0]
0x180013e70  xor     eax, eax
0x180013e72  mov     [rsp+38h+arg_0], ax
0x180013e77  mov     rax, [rcx]
0x180013e7a  mov     rax, [rax+40h]
0x180013e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e83  test    eax, eax
0x180013e85  js      short loc_180013EBF
0x180013e87  mov     rax, [rbx+8]
0x180013e8b  movzx   edx, [rsp+38h+arg_0]
0x180013e90  mov     rcx, [rax]
0x180013e93  mov     rax, [rcx]
0x180013e96  mov     rax, [rax+60h]
0x180013e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e9f  mov     edi, eax
0x180013ea1  test    eax, eax
0x180013ea3  jns     short loc_180013EBF
0x180013ea5  mov     r9d, 114h
0x180013eab  xor     edx, edx
0x180013ead  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013eb4  mov     ecx, edi
0x180013eb6  call    Log_HREvent
0x180013ebb  mov     eax, edi
0x180013ebd  jmp     short loc_180013EFE
0x180013ebf  mov     rcx, [rbx]
0x180013ec2  mov     edx, esi
0x180013ec4  mov     rax, [rcx]
0x180013ec7  mov     rax, [rax+38h]
0x180013ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ed0  mov     edi, eax
0x180013ed2  test    eax, eax
0x180013ed4  jns     short loc_180013EF5
0x180013ed6  mov     r8d, 119h
0x180013edc  lea     rdx, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013ee3  call    Log_AssertionEvent
0x180013ee8  mov     r9d, 11Ah
0x180013eee  mov     edx, 1
0x180013ef3  jmp     short loc_180013EAD
0x180013ef5  mov     dword ptr [rbx+14h], 0
0x180013efc  xor     eax, eax
0x180013efe  mov     rbx, [rsp+38h+arg_8]
0x180013f03  mov     rsi, [rsp+38h+arg_10]
0x180013f08  add     rsp, 30h
0x180013f0c  pop     rdi
0x180013f0d  retn
```

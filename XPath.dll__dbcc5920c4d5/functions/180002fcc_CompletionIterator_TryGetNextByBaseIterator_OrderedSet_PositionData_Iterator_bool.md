# CompletionIterator::TryGetNextByBaseIterator(OrderedSet<PositionData>::Iterator *,bool *)

- ea: `0x180002fcc`
- end: `0x1800030ab`
- name: `?TryGetNextByBaseIterator@CompletionIterator@@AEAAJPEAVIterator@?$OrderedSet@VPositionData@@@@PEA_N@Z`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002620`
- `0x180002a00`

## callees

- `0x1800020b4`
- `0x180002e9c`
- `0x180002fcc`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CompletionIterator::TryGetNextByBaseIterator(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rax
  int v9; // eax
  int v10; // ebx
  _BYTE v11[4]; // [rsp+20h] [rbp-38h] BYREF
  int v12; // [rsp+24h] [rbp-34h] BYREF
  __int64 v13[6]; // [rsp+28h] [rbp-30h] BYREF

  while ( 1 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 48LL))(*(_QWORD *)(a1 + 96));
    if ( (int)result < 0 )
      return result;
    if ( (_DWORD)result )
    {
      *(_BYTE *)(a1 + 24) = 1;
      *a3 = 0;
      return 0;
    }
    v7 = *(_QWORD *)(a1 + 96);
    v11[0] = 0;
    v12 = 0;
    v13[0] = 0;
    v8 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 72LL))(v7);
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v8 + 88LL))(*v8, v13);
    if ( v9 < 0 || (v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13[0] + 80LL))(v13[0], &v12), v9 < 0) )
    {
      v10 = v9;
LABEL_10:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
      return (unsigned int)v10;
    }
    v10 = OrderedSet<PositionData>::TryAdd(a1 + 32, v11, a2, a3);
    if ( v10 < 0 )
      goto LABEL_10;
    if ( *a3 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
      return 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
  }
}

```

## disassembly

```asm
0x180002fcc  push    rbx
0x180002fce  push    rbp
0x180002fcf  push    rsi
0x180002fd0  push    rdi
0x180002fd1  sub     rsp, 38h
0x180002fd5  mov     rdi, r8
0x180002fd8  mov     rbp, rdx
0x180002fdb  mov     rsi, rcx
0x180002fde  mov     rcx, [rsi+60h]
0x180002fe2  mov     rax, [rcx]
0x180002fe5  mov     rax, [rax+30h]
0x180002fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fee  test    eax, eax
0x180002ff0  js      loc_1800030A2
0x180002ff6  jnz     loc_180003099
0x180002ffc  mov     rcx, [rsi+60h]
0x180003000  mov     [rsp+58h+var_38], 0
0x180003005  mov     [rsp+58h+var_34], 0
0x18000300d  mov     [rsp+58h+var_30], 0
0x180003016  mov     rax, [rcx]
0x180003019  mov     rax, [rax+48h]
0x18000301d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003022  lea     rdx, [rsp+58h+var_30]
0x180003027  mov     rcx, [rax]
0x18000302a  mov     rax, [rcx]
0x18000302d  mov     rax, [rax+58h]
0x180003031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003036  test    eax, eax
0x180003038  js      short loc_180003089
0x18000303a  mov     rcx, [rsp+58h+var_30]
0x18000303f  lea     rdx, [rsp+58h+var_34]
0x180003044  mov     rax, [rcx]
0x180003047  mov     rax, [rax+50h]
0x18000304b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003050  test    eax, eax
0x180003052  js      short loc_180003089
0x180003054  lea     rcx, [rsi+20h]
0x180003058  mov     r9, rdi
0x18000305b  mov     r8, rbp
0x18000305e  lea     rdx, [rsp+58h+var_38]
0x180003063  call    ?TryAdd@?$OrderedSet@VPositionData@@@@QEAAJAEAVPositionData@@PEAVIterator@1@PEA_N@Z; OrderedSet<PositionData>::TryAdd(PositionData &,OrderedSet<PositionData>::Iterator *,bool *)
0x180003068  mov     ebx, eax
0x18000306a  test    eax, eax
0x18000306c  js      short loc_18000308B
0x18000306e  cmp     byte ptr [rdi], 0
0x180003071  lea     rcx, [rsp+58h+var_30]
0x180003076  jnz     short loc_180003082
0x180003078  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000307d  jmp     loc_180002FDE
0x180003082  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003087  jmp     short loc_1800030A0
0x180003089  mov     ebx, eax
0x18000308b  lea     rcx, [rsp+58h+var_30]
0x180003090  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003095  mov     eax, ebx
0x180003097  jmp     short loc_1800030A2
0x180003099  mov     byte ptr [rsi+18h], 1
0x18000309d  mov     byte ptr [rdi], 0
0x1800030a0  xor     eax, eax
0x1800030a2  add     rsp, 38h
0x1800030a6  pop     rdi
0x1800030a7  pop     rsi
0x1800030a8  pop     rbp
0x1800030a9  pop     rbx
0x1800030aa  retn
```

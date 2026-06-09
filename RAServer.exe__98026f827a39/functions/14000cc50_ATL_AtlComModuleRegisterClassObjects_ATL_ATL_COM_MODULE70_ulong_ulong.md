# ATL::AtlComModuleRegisterClassObjects(ATL::_ATL_COM_MODULE70 *,ulong,ulong)

- ea: `0x14000cc50`
- end: `0x14000cd12`
- name: `?AtlComModuleRegisterClassObjects@ATL@@YAJPEAU_ATL_COM_MODULE70@1@KK@Z`
- size: `194`
- prototype: `__int64 __fastcall(IUnknown *, __int64, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d798`

## callees

- `0x14000cc50`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000ccd5`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000ccd5`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleRegisterClassObjects(IUnknown *a1, __int64 a2, DWORD a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  __int64 *v5; // rax
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v7; // rsi
  bool v8; // zf
  LPUNKNOWN pUnk; // [rsp+60h] [rbp+8h] BYREF

  pUnk = a1;
  v3 = off_1400211F0;
  v5 = off_1400211F8;
  v6 = 1;
  while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 && v6 >= 0 )
  {
    v7 = *v3;
    if ( *v3 )
    {
      v8 = *((_QWORD *)v7 + 2) == 0;
      pUnk = 0;
      if ( v8 )
      {
        v6 = 0;
      }
      else
      {
        v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))v7 + 2))(
               *((_QWORD *)v7 + 3),
               &GUID_00000000_0000_0000_c000_000000000046,
               &pUnk);
        if ( v6 >= 0 )
          v6 = CoRegisterClassObject(*(const IID *const *)v7, pUnk, 4u, a3, (LPDWORD)v7 + 10);
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
        v5 = off_1400211F8;
      }
    }
    ++v3;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000cc50  mov     [rsp+pUnk], rcx
0x14000cc55  push    rbx
0x14000cc56  push    rbp
0x14000cc57  push    rsi
0x14000cc58  push    rdi
0x14000cc59  sub     rsp, 38h
0x14000cc5d  mov     rdi, cs:off_1400211F0
0x14000cc64  mov     ebp, r8d
0x14000cc67  mov     rax, cs:off_1400211F8
0x14000cc6e  mov     ebx, 1
0x14000cc73  jmp     loc_14000CCFE
0x14000cc78  test    ebx, ebx
0x14000cc7a  js      loc_14000CD07
0x14000cc80  mov     rsi, [rdi]
0x14000cc83  test    rsi, rsi
0x14000cc86  jz      short loc_14000CCFA
0x14000cc88  cmp     qword ptr [rsi+10h], 0
0x14000cc8d  mov     [rsp+58h+pUnk], 0
0x14000cc96  jnz     short loc_14000CC9C
0x14000cc98  xor     ebx, ebx
0x14000cc9a  jmp     short loc_14000CCFA
0x14000cc9c  mov     rcx, [rsi+18h]
0x14000cca0  lea     r8, [rsp+58h+pUnk]
0x14000cca5  mov     rax, [rsi+10h]
0x14000cca9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000ccb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccb5  mov     ebx, eax
0x14000ccb7  test    eax, eax
0x14000ccb9  js      short loc_14000CCDD
0x14000ccbb  mov     rdx, [rsp+58h+pUnk]; pUnk
0x14000ccc0  lea     rax, [rsi+28h]
0x14000ccc4  mov     rcx, [rsi]; rclsid
0x14000ccc7  mov     r9d, ebp; flags
0x14000ccca  mov     r8d, 4; dwClsContext
0x14000ccd0  mov     [rsp+58h+lpdwRegister], rax; lpdwRegister
0x14000ccd5  call    cs:__imp_CoRegisterClassObject
0x14000ccdb  mov     ebx, eax
0x14000ccdd  mov     rcx, [rsp+58h+pUnk]
0x14000cce2  test    rcx, rcx
0x14000cce5  jz      short loc_14000CCF3
0x14000cce7  mov     rax, [rcx]
0x14000ccea  mov     rax, [rax+10h]
0x14000ccee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccf3  mov     rax, cs:off_1400211F8
0x14000ccfa  add     rdi, 8
0x14000ccfe  cmp     rdi, rax
0x14000cd01  jb      loc_14000CC78
0x14000cd07  mov     eax, ebx
0x14000cd09  add     rsp, 38h
0x14000cd0d  pop     rdi
0x14000cd0e  pop     rsi
0x14000cd0f  pop     rbp
0x14000cd10  pop     rbx
0x14000cd11  retn
```

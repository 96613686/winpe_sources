# CEnhancedStorageEnumerator::FinalRelease(void)

- ea: `0x1800034b0`
- end: `0x18000355c`
- name: `?FinalRelease@CEnhancedStorageEnumerator@@QEAAXXZ`
- size: `172`
- prototype: `void __fastcall(CEnhancedStorageEnumerator *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003450`

## callees

- `0x1800034b0`
- `0x18000684c`
- `0x18000c010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003512`
- `ole32!CoTaskMemFree` at `0x180003512`

## pseudocode

```c
void __fastcall CEnhancedStorageEnumerator::FinalRelease(
        CEnhancedStorageEnumerator *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rcx
  unsigned int i; // edi
  __int64 v7; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, a4);
  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; i < *((_DWORD *)this + 7); ++i )
    {
      v7 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * i);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    CoTaskMemFree(*((LPVOID *)this + 4));
    *((_QWORD *)this + 4) = 0;
    *((_DWORD *)this + 7) = 0;
  }
  v5 = *((_QWORD *)this + 2);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800034b0  mov     [rsp+arg_8], rbx
0x1800034b5  push    rsi
0x1800034b6  sub     rsp, 20h
0x1800034ba  mov     rbx, rcx
0x1800034bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034c4  lea     rax, WPP_GLOBAL_Control
0x1800034cb  cmp     rcx, rax
0x1800034ce  jz      short loc_1800034D6
0x1800034d0  test    byte ptr [rcx+1Ch], 20h
0x1800034d4  jnz     short loc_180003526
0x1800034d6  xor     esi, esi
0x1800034d8  cmp     [rbx+20h], rsi
0x1800034dc  jnz     short loc_180003502
0x1800034de  mov     rcx, [rbx+10h]
0x1800034e2  test    rcx, rcx
0x1800034e5  jz      short loc_1800034F7
0x1800034e7  mov     rax, [rcx]
0x1800034ea  mov     rax, [rax+10h]
0x1800034ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f3  mov     [rbx+10h], rsi
0x1800034f7  mov     rbx, [rsp+28h+arg_8]
0x1800034fc  add     rsp, 20h
0x180003500  pop     rsi
0x180003501  retn
0x180003502  mov     [rsp+28h+arg_0], rdi
0x180003507  mov     edi, esi
0x180003509  cmp     [rbx+1Ch], esi
0x18000350c  ja      short loc_18000353D
0x18000350e  mov     rcx, [rbx+20h]; pv
0x180003512  call    cs:__imp_CoTaskMemFree
0x180003518  mov     rdi, [rsp+28h+arg_0]
0x18000351d  mov     [rbx+20h], rsi
0x180003521  mov     [rbx+1Ch], esi
0x180003524  jmp     short loc_1800034DE
0x180003526  mov     rcx, [rcx+10h]
0x18000352a  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180003531  mov     edx, 0Eh
0x180003536  call    WPP_SF_
0x18000353b  jmp     short loc_1800034D6
0x18000353d  mov     rax, [rbx+20h]
0x180003541  mov     ecx, edi
0x180003543  mov     rcx, [rax+rcx*8]
0x180003547  mov     rax, [rcx]
0x18000354a  mov     rax, [rax+10h]
0x18000354e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003553  inc     edi
0x180003555  cmp     edi, [rbx+1Ch]
0x180003558  jb      short loc_18000353D
0x18000355a  jmp     short loc_18000350E
```

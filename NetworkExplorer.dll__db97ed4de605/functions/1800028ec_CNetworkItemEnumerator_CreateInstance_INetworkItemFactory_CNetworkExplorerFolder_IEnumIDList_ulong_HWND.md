# CNetworkItemEnumerator_CreateInstance(INetworkItemFactory *,CNetworkExplorerFolder *,IEnumIDList * *,ulong,HWND__ *)

- ea: `0x1800028ec`
- end: `0x180002981`
- name: `?CNetworkItemEnumerator_CreateInstance@@YAJPEAUINetworkItemFactory@@PEAVCNetworkExplorerFolder@@PEAPEAUIEnumIDList@@KPEAUHWND__@@@Z`
- size: `149`
- prototype: `__int64 __usercall@<rax>(struct INetworkItemFactory *@<rcx>, struct CNetworkExplorerFolder *@<rdx>, struct IEnumIDList **@<r8>, unsigned int@<r9d>, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800027b0`

## callees

- `0x1800028ec`
- `0x180002a90`
- `0x180002abc`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetworkItemEnumerator_CreateInstance(
        struct INetworkItemFactory *a1,
        struct CNetworkExplorerFolder *a2,
        struct IEnumIDList **a3,
        unsigned int a4,
        HWND a5)
{
  CNetworkItemEnumerator *v9; // rax
  CNetworkItemEnumerator *v10; // rbx
  unsigned int v11; // edi

  *a3 = 0;
  v9 = (CNetworkItemEnumerator *)operator new(0x50u);
  if ( v9 )
    v10 = CNetworkItemEnumerator::CNetworkItemEnumerator(v9, a1, a2, a4, a5);
  else
    v10 = 0;
  if ( v10 )
  {
    v11 = (**(__int64 (__fastcall ***)(CNetworkItemEnumerator *, GUID *, struct IEnumIDList **))v10)(
            v10,
            &GUID_000214f2_0000_0000_c000_000000000046,
            a3);
    (*(void (__fastcall **)(CNetworkItemEnumerator *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v11;
}

```

## disassembly

```asm
0x1800028ec  push    rbx
0x1800028ee  push    rbp
0x1800028ef  push    rsi
0x1800028f0  push    rdi
0x1800028f1  sub     rsp, 38h
0x1800028f5  mov     ebx, r9d
0x1800028f8  mov     rdi, r8
0x1800028fb  mov     rsi, rdx
0x1800028fe  mov     rbp, rcx
0x180002901  mov     qword ptr [r8], 0
0x180002908  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000290d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002912  mov     [rsp+58h+arg_10], rax
0x180002917  test    rax, rax
0x18000291a  jz      short loc_180002952
0x18000291c  mov     r8, [rsp+58h+arg_20]
0x180002924  mov     [rsp+58h+var_38], r8; HWND
0x180002929  mov     r9d, ebx; unsigned int
0x18000292c  mov     r8, rsi; struct CNetworkExplorerFolder *
0x18000292f  mov     rdx, rbp; struct INetworkItemFactory *
0x180002932  mov     rcx, rax; this
0x180002935  call    ??0CNetworkItemEnumerator@@QEAA@PEAUINetworkItemFactory@@PEAVCNetworkExplorerFolder@@KPEAUHWND__@@@Z; CNetworkItemEnumerator::CNetworkItemEnumerator(INetworkItemFactory *,CNetworkExplorerFolder *,ulong,HWND__ *)
0x18000293a  mov     rbx, rax
0x18000293d  test    rbx, rbx
0x180002940  jnz     short loc_180002956
0x180002942  mov     edi, 8007000Eh
0x180002947  mov     eax, edi
0x180002949  add     rsp, 38h
0x18000294d  pop     rdi
0x18000294e  pop     rsi
0x18000294f  pop     rbp
0x180002950  pop     rbx
0x180002951  retn
0x180002952  xor     ebx, ebx
0x180002954  jmp     short loc_18000293D
0x180002956  mov     rax, [rbx]
0x180002959  mov     r8, rdi
0x18000295c  lea     rdx, _GUID_000214f2_0000_0000_c000_000000000046
0x180002963  mov     rcx, rbx
0x180002966  mov     rax, [rax]
0x180002969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000296e  mov     edi, eax
0x180002970  mov     rcx, [rbx]
0x180002973  mov     rax, [rcx+10h]
0x180002977  mov     rcx, rbx
0x18000297a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000297f  jmp     short loc_180002947
```

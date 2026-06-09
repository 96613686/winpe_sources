# WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfileCollection>::IsOtherObjectInstanceNameCompatible(IUnknown *)

- ea: `0x18002fce0`
- end: `0x18002fe1d`
- name: `?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfileCollection@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z`
- size: `317`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002f980`
- `0x18006eb90`
- `0x18006f130`
- `0x180071490`

## callees

- `0x18001e6e0`
- `0x18002fce0`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002fdee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fdfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fe07`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fdee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fdfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fe07`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18002fdd9`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18002fdd9`

## string_xrefs

- `0x18002fd61`: `COMGUARD`
- `0x18002fd76`: `IsOtherObjectInstanceNameCompatible`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfileCollection>::IsOtherObjectInstanceNameCompatible(
        __int64 a1,
        void (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  signed int v4; // ebx
  const char *v5; // [rsp+28h] [rbp-20h]
  __int64 v6; // [rsp+58h] [rbp+10h] BYREF
  BSTR bstrRight; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  bstrRight = 0;
  v6 = 0;
  (**a2)(a2, &GUID_00383df6_90fc_49c0_b65e_0b585bdfddda, &v6);
  if ( !v6 )
  {
    v4 = -2147418113;
LABEL_15:
    SysFreeString(bstrRight);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v6 + 40LL))(v6, &bstrRight);
  if ( v4 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "IsOtherObjectInstanceNameCompatible",
      (const char *)0xA0,
      v4,
      "COMGUARD",
      v5);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    goto LABEL_15;
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( *(_QWORD *)(a1 + 8) && bstrRight )
  {
    if ( VarBstrCmp(*(BSTR *)(a1 + 8), bstrRight, 0x400u, 0) != 1 )
    {
      v4 = -984087013;
      goto LABEL_15;
    }
    SysFreeString(bstrRight);
    return 0;
  }
  else
  {
    SysFreeString(bstrRight);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18002fce0  push    rdi
0x18002fce2  sub     rsp, 40h
0x18002fce6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002fcef  mov     [rsp+48h+arg_0], rbx
0x18002fcf4  mov     r9, rdx
0x18002fcf7  mov     rdi, rcx
0x18002fcfa  test    rdx, rdx
0x18002fcfd  jnz     short loc_18002FD09
0x18002fcff  mov     eax, 80004003h
0x18002fd04  jmp     loc_18002FE12
0x18002fd09  mov     [rsp+48h+bstrRight], 0
0x18002fd12  mov     [rsp+48h+arg_8], 0
0x18002fd1b  mov     rax, [rdx]
0x18002fd1e  lea     r8, [rsp+48h+arg_8]
0x18002fd23  lea     rdx, _GUID_00383df6_90fc_49c0_b65e_0b585bdfddda
0x18002fd2a  mov     rcx, r9
0x18002fd2d  mov     rax, [rax]
0x18002fd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd35  nop
0x18002fd36  mov     rcx, [rsp+48h+arg_8]
0x18002fd3b  test    rcx, rcx
0x18002fd3e  jnz     short loc_18002FD4A
0x18002fd40  mov     ebx, 8000FFFFh
0x18002fd45  jmp     loc_18002FDE9
0x18002fd4a  mov     rax, [rcx]
0x18002fd4d  lea     rdx, [rsp+48h+bstrRight]
0x18002fd52  mov     rax, [rax+28h]
0x18002fd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd5b  mov     ebx, eax
0x18002fd5d  test    eax, eax
0x18002fd5f  jns     short loc_18002FDA1
0x18002fd61  lea     rax, aComguard; "COMGUARD"
0x18002fd68  mov     [rsp+48h+Format], rax; Format
0x18002fd6d  mov     r9d, ebx; unsigned int
0x18002fd70  mov     r8d, 0A0h; char *
0x18002fd76  lea     rdx, aIsotherobjecti; "IsOtherObjectInstanceNameCompatible"
0x18002fd7d  mov     ecx, 2; this
0x18002fd82  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18002fd87  nop
0x18002fd88  mov     rcx, [rsp+48h+arg_8]
0x18002fd8d  test    rcx, rcx
0x18002fd90  jz      short loc_18002FD9F
0x18002fd92  mov     rax, [rcx]
0x18002fd95  mov     rax, [rax+10h]
0x18002fd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd9e  nop
0x18002fd9f  jmp     short loc_18002FDE9
0x18002fda1  mov     rcx, [rsp+48h+arg_8]
0x18002fda6  test    rcx, rcx
0x18002fda9  jz      short loc_18002FDB8
0x18002fdab  mov     rax, [rcx]
0x18002fdae  mov     rax, [rax+10h]
0x18002fdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdb7  nop
0x18002fdb8  mov     rcx, [rsp+48h+bstrRight]; bstrString
0x18002fdbd  cmp     qword ptr [rdi+8], 0
0x18002fdc2  jz      short loc_18002FE07
0x18002fdc4  test    rcx, rcx
0x18002fdc7  jz      short loc_18002FE07
0x18002fdc9  xor     r9d, r9d; dwFlags
0x18002fdcc  mov     r8d, 400h; lcid
0x18002fdd2  mov     rdx, rcx; bstrRight
0x18002fdd5  mov     rcx, [rdi+8]; bstrLeft
0x18002fdd9  call    cs:__imp_VarBstrCmp
0x18002fddf  cmp     eax, 1
0x18002fde2  jz      short loc_18002FDF8
0x18002fde4  mov     ebx, 0C558061Bh
0x18002fde9  mov     rcx, [rsp+48h+bstrRight]; bstrString
0x18002fdee  call    cs:__imp_SysFreeString
0x18002fdf4  mov     eax, ebx
0x18002fdf6  jmp     short loc_18002FE12
0x18002fdf8  mov     rcx, [rsp+48h+bstrRight]; bstrString
0x18002fdfd  call    cs:__imp_SysFreeString
0x18002fe03  xor     eax, eax
0x18002fe05  jmp     short loc_18002FE12
0x18002fe07  call    cs:__imp_SysFreeString
0x18002fe0d  mov     eax, 8000FFFFh
0x18002fe12  mov     rbx, [rsp+48h+arg_0]
0x18002fe17  add     rsp, 40h
0x18002fe1b  pop     rdi
0x18002fe1c  retn
```

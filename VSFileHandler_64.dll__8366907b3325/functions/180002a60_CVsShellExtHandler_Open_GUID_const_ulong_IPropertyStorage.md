# CVsShellExtHandler::Open(_GUID const &,ulong,IPropertyStorage * *)

- ea: `0x180002a60`
- end: `0x180002b12`
- name: `?Open@CVsShellExtHandler@@UEAAJAEBU_GUID@@KPEAPEAUIPropertyStorage@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(CVsShellExtHandler *__hidden this, const struct _GUID *, unsigned int, struct IPropertyStorage **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002a60`
- `0x180007d74`

## pseudocode

```c
__int64 __fastcall CVsShellExtHandler::Open(
        CVsShellExtHandler *this,
        const struct _GUID *a2,
        __int64 a3,
        struct IPropertyStorage **a4)
{
  unsigned int v7; // r8d
  char *v8; // rbx
  __int128 v9; // xmm0

  *a4 = 0;
  v7 = -2147287038;
  if ( *(_OWORD *)a2 == *(_OWORD *)&FMTID_SummaryInformation )
  {
    v8 = (char *)operator new(0x28u);
    *(_QWORD *)(v8 + 12) = 0;
    *(_QWORD *)(v8 + 20) = 0;
    *(_QWORD *)(v8 + 28) = 0;
    *((_DWORD *)v8 + 9) = 0;
    *(_QWORD *)v8 = &CDocInfoPropertyStg::`vftable';
    *((_DWORD *)v8 + 2) = 1;
    v9 = (__int128)*a2;
    *((_QWORD *)v8 + 4) = (char *)this - 16;
    *(_OWORD *)(v8 + 12) = v9;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 8LL))((char *)this - 16);
    *a4 = (struct IPropertyStorage *)v8;
    return v8 == 0 ? 0x8007000E : 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180002a60  mov     [rsp+arg_0], rbx
0x180002a65  mov     [rsp+arg_8], rbp
0x180002a6a  mov     [rsp+arg_10], rsi
0x180002a6f  push    rdi
0x180002a70  sub     rsp, 20h
0x180002a74  and     qword ptr [r9], 0
0x180002a78  mov     rsi, r9
0x180002a7b  mov     rax, [rdx]
0x180002a7e  mov     rdi, rdx
0x180002a81  cmp     rax, qword ptr cs:FMTID_SummaryInformation.Data1
0x180002a88  mov     rbp, rcx
0x180002a8b  mov     r8d, 80030002h
0x180002a91  jnz     short loc_180002AFA
0x180002a93  mov     rax, [rdx+8]
0x180002a97  cmp     rax, qword ptr cs:FMTID_SummaryInformation.Data4
0x180002a9e  jnz     short loc_180002AFA
0x180002aa0  mov     ecx, 28h ; '('; Size
0x180002aa5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002aaa  mov     rbx, rax
0x180002aad  lea     rcx, [rbp-10h]
0x180002ab1  and     qword ptr [rax+0Ch], 0
0x180002ab6  and     qword ptr [rax+14h], 0
0x180002abb  and     qword ptr [rax+1Ch], 0
0x180002ac0  and     dword ptr [rax+24h], 0
0x180002ac4  lea     rax, ??_7CDocInfoPropertyStg@@6B@; const CDocInfoPropertyStg::`vftable'
0x180002acb  mov     [rbx], rax
0x180002ace  mov     dword ptr [rbx+8], 1
0x180002ad5  movups  xmm0, xmmword ptr [rdi]
0x180002ad8  mov     [rbx+20h], rcx
0x180002adc  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180002ae1  mov     rax, [rcx]
0x180002ae4  call    qword ptr [rax+8]
0x180002ae7  mov     [rsi], rbx
0x180002aea  neg     rbx
0x180002aed  sbb     r8d, r8d
0x180002af0  not     r8d
0x180002af3  and     r8d, 8007000Eh
0x180002afa  mov     rbx, [rsp+28h+arg_0]
0x180002aff  mov     eax, r8d
0x180002b02  mov     rbp, [rsp+28h+arg_8]
0x180002b07  mov     rsi, [rsp+28h+arg_10]
0x180002b0c  add     rsp, 20h
0x180002b10  pop     rdi
0x180002b11  retn
```

# utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(void)

- ea: `0x18000186c`
- end: `0x1800018c6`
- name: `??$make_unique@USimplifiedSpecificKey@Kerb3961@@$$V$0A@@utl@@YA?AV?$unique_ptr@USimplifiedSpecificKey@Kerb3961@@U?$default_delete@USimplifiedSpecificKey@Kerb3961@@@utl@@@0@XZ`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004390`
- `0x180008020`

## callees

- `0x18000186c`
- `0x180011ab8`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(_QWORD *a1, const struct std::nothrow_t *a2)
{
  _DWORD *v3; // rax

  v3 = operator new[](0x48u, a2);
  if ( v3 )
  {
    v3[5] = 0;
    v3[11] = 0;
    v3[17] = 0;
    *(_QWORD *)v3 = 0;
    *((_QWORD *)v3 + 1) = 0;
    v3[4] = -1073741823;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 4) = 0;
    v3[10] = -1073741823;
    *((_QWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 7) = 0;
    v3[16] = -1073741823;
  }
  else
  {
    v3 = 0;
  }
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x18000186c  push    rbx
0x18000186e  sub     rsp, 20h
0x180001872  mov     rbx, rcx
0x180001875  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000187a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000187f  xor     edx, edx
0x180001881  test    rax, rax
0x180001884  jz      short loc_1800018B6
0x180001886  mov     [rax+14h], edx
0x180001889  mov     ecx, 0C0000001h
0x18000188e  mov     [rax+2Ch], edx
0x180001891  mov     [rax+44h], edx
0x180001894  mov     [rax], rdx
0x180001897  mov     [rax+8], rdx
0x18000189b  mov     [rax+10h], ecx
0x18000189e  mov     [rax+18h], rdx
0x1800018a2  mov     [rax+20h], rdx
0x1800018a6  mov     [rax+28h], ecx
0x1800018a9  mov     [rax+30h], rdx
0x1800018ad  mov     [rax+38h], rdx
0x1800018b1  mov     [rax+40h], ecx
0x1800018b4  jmp     short loc_1800018B9
0x1800018b6  mov     rax, rdx
0x1800018b9  mov     [rbx], rax
0x1800018bc  mov     rax, rbx
0x1800018bf  add     rsp, 20h
0x1800018c3  pop     rbx
0x1800018c4  retn
```

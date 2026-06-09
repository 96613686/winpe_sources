# WICCreateColorTransform_Proxy

- ea: `0x180009530`
- end: `0x180009589`
- name: `WICCreateColorTransform_Proxy`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180009530`
- `0x180009590`
- `0x1800215e8`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall WICCreateColorTransform_Proxy(_QWORD *a1)
{
  __int64 result; // rax
  CIcmColorTransform *v3; // rax
  CIcmColorTransform *v4; // rcx

  result = 2147942487LL;
  if ( a1 )
  {
    v3 = (CIcmColorTransform *)operator new(0x130u);
    if ( v3 )
    {
      v4 = CIcmColorTransform::CIcmColorTransform(v3);
      result = 2147942414LL;
      if ( v4 )
      {
        *a1 = (char *)v4 + 80;
        (*(void (__fastcall **)(CIcmColorTransform *))(*(_QWORD *)v4 + 8LL))(v4);
        return 0;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009530  push    rbx
0x180009532  sub     rsp, 20h
0x180009536  mov     rbx, rcx
0x180009539  mov     eax, 80070057h
0x18000953e  test    rcx, rcx
0x180009541  jz      short loc_18000957C
0x180009543  mov     ecx, 130h; Size
0x180009548  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000954d  test    rax, rax
0x180009550  jz      short loc_180009582
0x180009552  mov     rcx, rax; this
0x180009555  call    ??0CIcmColorTransform@@QEAA@XZ; CIcmColorTransform::CIcmColorTransform(void)
0x18000955a  mov     rcx, rax
0x18000955d  mov     eax, 8007000Eh
0x180009562  test    rcx, rcx
0x180009565  jz      short loc_18000957C
0x180009567  lea     rax, [rcx+50h]
0x18000956b  mov     [rbx], rax
0x18000956e  mov     rax, [rcx]
0x180009571  mov     rax, [rax+8]
0x180009575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000957a  xor     eax, eax
0x18000957c  add     rsp, 20h
0x180009580  pop     rbx
0x180009581  retn
0x180009582  mov     eax, 8007000Eh
0x180009587  jmp     short loc_18000957C
```

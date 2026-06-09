# MitigationOptionsPolicy::ImagePolicy::EnableSehOverwriteProtection(bool *,bool *)

- ea: `0x18001246c`
- end: `0x1800124cc`
- name: `?EnableSehOverwriteProtection@ImagePolicy@MitigationOptionsPolicy@@QEBAEPEA_N0@Z`
- size: `96`
- prototype: `unsigned __int8 __fastcall(MitigationOptionsPolicy::ImagePolicy *__hidden this, bool *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007918`

## callees

- `0x18001081c`
- `0x18001246c`

## pseudocode

```c
unsigned __int8 __fastcall MitigationOptionsPolicy::ImagePolicy::EnableSehOverwriteProtection(
        MitigationOptionsPolicy::ImagePolicy *this,
        bool *a2,
        bool *a3)
{
  unsigned __int8 result; // al
  __int64 v6; // r10
  bool v7; // cl

  result = MitigationOptionsPolicy::Policy::GetOptionState(*((_BYTE *)this + 3024) & 3, *((_BYTE *)this + 3032) & 3);
  v7 = (result & 2) != 0 && (*(_BYTE *)(v6 + 3024) & 8) != 0;
  *a2 = v7;
  *a3 = (*(_BYTE *)(v6 + 3024) & 4) != 0;
  return result;
}

```

## disassembly

```asm
0x18001246c  mov     [rsp+arg_0], rbx
0x180012471  push    rdi
0x180012472  sub     rsp, 20h
0x180012476  mov     r10, rcx
0x180012479  mov     rdi, rdx
0x18001247c  mov     dl, [rcx+0BD8h]
0x180012482  mov     rbx, r8
0x180012485  mov     cl, [rcx+0BD0h]
0x18001248b  and     dl, 3; unsigned __int8
0x18001248e  and     cl, 3; unsigned __int8
0x180012491  call    ?GetOptionState@Policy@MitigationOptionsPolicy@@KAEEE@Z; MitigationOptionsPolicy::Policy::GetOptionState(uchar,uchar)
0x180012496  mov     r11b, al
0x180012499  test    al, 2
0x18001249b  jz      short loc_1800124AC
0x18001249d  mov     cl, [r10+0BD0h]
0x1800124a4  shr     cl, 3
0x1800124a7  and     cl, 1
0x1800124aa  jmp     short loc_1800124AE
0x1800124ac  xor     cl, cl
0x1800124ae  mov     [rdi], cl
0x1800124b0  mov     al, [r10+0BD0h]
0x1800124b7  shr     al, 2
0x1800124ba  and     al, 1
0x1800124bc  mov     [rbx], al
0x1800124be  mov     al, r11b
0x1800124c1  mov     rbx, [rsp+28h+arg_0]
0x1800124c6  add     rsp, 20h
0x1800124ca  pop     rdi
0x1800124cb  retn
```

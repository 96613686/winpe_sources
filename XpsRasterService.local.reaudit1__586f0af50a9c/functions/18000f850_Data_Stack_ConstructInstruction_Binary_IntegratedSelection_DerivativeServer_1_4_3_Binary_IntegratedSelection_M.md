# Data::Stack::ConstructInstruction<Binary::IntegratedSelection::DerivativeServer<1,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>,64>::CallComplexSkill(void)

- ea: `0x18000f850`
- end: `0x18000f8b1`
- name: `?CallComplexSkill@?$ConstructInstruction@V?$DerivativeServer@$00$03$02V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@$0EA@@Stack@Data@@AEAAXXZ`
- size: `97`
- prototype: ``
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e5d0`
- `0x18000e630`
- `0x180011680`
- `0x180059140`
- `0x180059800`
- `0x180059930`
- `0x180059b00`
- `0x180059c30`
- `0x180059d60`
- `0x180059e90`
- `0x18005a060`
- `0x18005a190`
- `0x18005a2c0`
- `0x18005a530`
- `0x18005a700`
- `0x18005a830`
- `0x180066570`
- `0x180067420`
- `0x18006ba30`
- `0x18006bbd0`
- `0x18006bd70`
- `0x18006bf10`
- `0x18006c0b0`
- `0x18006c250`
- `0x18006c3f0`
- `0x18006c590`
- `0x18006c730`
- `0x18006c8d0`

## callees

- `0x18000f850`
- `0x1800bf3b0`

## pseudocode

```c
__int64 __fastcall Data::Stack::ConstructInstruction<Binary::IntegratedSelection::DerivativeServer<1,4,3,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>,64>::CallComplexSkill(
        __int64 *a1)
{
  __int64 v1; // rbx
  void (__fastcall ***v3)(_QWORD, _QWORD); // rcx
  __int64 v4; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( (int)--*(_DWORD *)v1 <= 0 )
    {
      v3 = *(void (__fastcall ****)(_QWORD, _QWORD))(v1 + 8);
      if ( v3 )
        (**v3)(v3, 0);
      v4 = *(_QWORD *)(v1 + 24);
      *(_QWORD *)(v1 + 8) = 0;
      result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 8LL))(v4, v1);
    }
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f850  mov     [rsp+arg_0], rbx
0x18000f855  push    rdi
0x18000f856  sub     rsp, 20h
0x18000f85a  mov     rbx, [rcx]
0x18000f85d  mov     rdi, rcx
0x18000f860  test    rbx, rbx
0x18000f863  jz      short loc_18000F8A6
0x18000f865  dec     dword ptr [rbx]
0x18000f867  cmp     dword ptr [rbx], 0
0x18000f86a  jg      short loc_18000F89F
0x18000f86c  mov     rcx, [rbx+8]
0x18000f870  test    rcx, rcx
0x18000f873  jz      short loc_18000F883
0x18000f875  mov     rax, [rcx]
0x18000f878  xor     edx, edx
0x18000f87a  mov     rax, [rax]
0x18000f87d  call    cs:__guard_dispatch_icall_fptr
0x18000f883  mov     rcx, [rbx+18h]
0x18000f887  mov     rdx, rbx
0x18000f88a  mov     qword ptr [rbx+8], 0
0x18000f892  mov     rax, [rcx]
0x18000f895  mov     rax, [rax+8]
0x18000f899  call    cs:__guard_dispatch_icall_fptr
0x18000f89f  mov     qword ptr [rdi], 0
0x18000f8a6  mov     rbx, [rsp+28h+arg_0]
0x18000f8ab  add     rsp, 20h
0x18000f8af  pop     rdi
0x18000f8b0  retn
```

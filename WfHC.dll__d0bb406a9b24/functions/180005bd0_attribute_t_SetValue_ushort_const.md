# _attribute_t::SetValue(ushort const *)

- ea: `0x180005bd0`
- end: `0x180005c50`
- name: `?SetValue@_attribute_t@@QEAAJPEBG@Z`
- size: `128`
- prototype: `__int64 __fastcall(_attribute_t *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800031e0`

## callees

- `0x180005bd0`
- `0x180005ce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005bec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005bec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c05`

## pseudocode

```c
__int64 __fastcall _attribute_t::SetValue(_attribute_t *this, const unsigned __int16 *a2)
{
  int v2; // eax
  __int64 result; // rax
  int v6; // ecx
  int v7; // eax

  v2 = *((_DWORD *)this + 2);
  if ( v2 == 10 )
  {
    CoTaskMemFree(*((LPVOID *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  else if ( v2 == 14 )
  {
    CoTaskMemFree(*((LPVOID *)this + 3));
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 4) = 0;
  }
  result = 0;
  if ( a2 )
  {
    v6 = StringCchCopyWithAlloc((unsigned __int16 **)this + 2, 0xFFFFu, a2);
    v7 = 0;
    if ( v6 >= 0 )
      v7 = 10;
    *((_DWORD *)this + 2) = v7;
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180005bd0  mov     [rsp+arg_0], rbx
0x180005bd5  push    rdi
0x180005bd6  sub     rsp, 20h
0x180005bda  mov     eax, [rcx+8]
0x180005bdd  mov     rdi, rdx
0x180005be0  mov     rbx, rcx
0x180005be3  cmp     eax, 0Ah
0x180005be6  jnz     short loc_180005BFC
0x180005be8  mov     rcx, [rcx+10h]; pv
0x180005bec  call    cs:__imp_CoTaskMemFree
0x180005bf2  mov     qword ptr [rbx+10h], 0
0x180005bfa  jmp     short loc_180005C1A
0x180005bfc  cmp     eax, 0Eh
0x180005bff  jnz     short loc_180005C1A
0x180005c01  mov     rcx, [rcx+18h]; pv
0x180005c05  call    cs:__imp_CoTaskMemFree
0x180005c0b  mov     qword ptr [rbx+18h], 0
0x180005c13  mov     dword ptr [rbx+10h], 0
0x180005c1a  xor     eax, eax
0x180005c1c  test    rdi, rdi
0x180005c1f  jz      short loc_180005C45
0x180005c21  lea     rcx, [rbx+10h]; unsigned __int16 **
0x180005c25  mov     r8, rdi; unsigned __int16 *
0x180005c28  mov     edx, 0FFFFh; unsigned __int64
0x180005c2d  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180005c32  mov     ecx, eax
0x180005c34  mov     edx, 0Ah
0x180005c39  xor     eax, eax
0x180005c3b  test    ecx, ecx
0x180005c3d  cmovns  eax, edx
0x180005c40  mov     [rbx+8], eax
0x180005c43  mov     eax, ecx
0x180005c45  mov     rbx, [rsp+28h+arg_0]
0x180005c4a  add     rsp, 20h
0x180005c4e  pop     rdi
0x180005c4f  retn
```

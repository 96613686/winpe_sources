# AuthHostWebInstance::GetUserAgentToken(ushort * *)

- ea: `0x140005420`
- end: `0x1400054ba`
- name: `?GetUserAgentToken@AuthHostWebInstance@@UEAAJPEAPEAG@Z`
- size: `154`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140005420`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140005494`
- `OLEAUT32!__imp_SysAllocString` at `0x140005494`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::GetUserAgentToken(AuthHostWebInstance *this, unsigned __int16 **a2)
{
  bool v2; // zf
  unsigned __int16 *v5; // rax
  OLECHAR *psz[3]; // [rsp+20h] [rbp-18h]

  v2 = (*((_DWORD *)this + 32) & 0x100000) == 0;
  psz[0] = L"MSAuthHost/1.0";
  psz[1] = L"MSAuthHost/1.0/In-Domain";
  if ( !v2 && !*((_DWORD *)this + 175) )
  {
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 160LL))(
      *((_QWORD *)this + 13),
      (char *)this + 696);
    *((_DWORD *)this + 175) = 1;
  }
  v5 = SysAllocString(*(OLECHAR **)((char *)psz + (*((_DWORD *)this + 174) != 0 ? 8 : 0)));
  *a2 = v5;
  return v5 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140005420  mov     [rsp+arg_0], rbx
0x140005425  push    rdi
0x140005426  sub     rsp, 30h
0x14000542a  test    dword ptr [rcx+80h], 100000h
0x140005434  lea     rax, aMsauthhost10; "MSAuthHost/1.0"
0x14000543b  mov     [rsp+38h+psz], rax
0x140005440  mov     rdi, rdx
0x140005443  lea     rax, aMsauthhost10In; "MSAuthHost/1.0/In-Domain"
0x14000544a  mov     rbx, rcx
0x14000544d  mov     [rsp+38h+var_10], rax
0x140005452  jz      short loc_140005481
0x140005454  cmp     dword ptr [rcx+2BCh], 0
0x14000545b  jnz     short loc_140005481
0x14000545d  mov     rcx, [rcx+68h]
0x140005461  lea     rdx, [rbx+2B8h]
0x140005468  mov     rax, [rcx]
0x14000546b  mov     rax, [rax+0A0h]
0x140005472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005477  mov     dword ptr [rbx+2BCh], 1
0x140005481  mov     eax, [rbx+2B8h]
0x140005487  neg     eax
0x140005489  sbb     rcx, rcx
0x14000548c  and     ecx, 8
0x14000548f  mov     rcx, [rsp+rcx+38h+psz]; psz
0x140005494  call    cs:__imp_SysAllocString
0x14000549a  mov     rbx, [rsp+38h+arg_0]
0x14000549f  mov     rcx, rax
0x1400054a2  mov     rdx, rax
0x1400054a5  neg     rcx
0x1400054a8  mov     [rdi], rdx
0x1400054ab  sbb     eax, eax
0x1400054ad  not     eax
0x1400054af  and     eax, 8007000Eh
0x1400054b4  add     rsp, 30h
0x1400054b8  pop     rdi
0x1400054b9  retn
```

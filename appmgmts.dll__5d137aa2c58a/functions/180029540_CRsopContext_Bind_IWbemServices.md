# CRsopContext::Bind(IWbemServices * *)

- ea: `0x180029540`
- end: `0x1800295ae`
- name: `?Bind@CRsopContext@@QEAAJPEAPEAUIWbemServices@@@Z`
- size: `110`
- prototype: `int __fastcall(const unsigned __int16 **this, struct IWbemServices **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000c790`
- `0x18002a754`

## callees

- `0x180029540`
- `0x180029abc`

## pseudocode

```c
int __fastcall CRsopContext::Bind(const unsigned __int16 **this, struct IWbemServices **a2)
{
  int result; // eax
  struct IWbemServices **v3; // rdi
  int *v6; // rcx

  result = 0;
  v3 = (struct IWbemServices **)(this + 1);
  if ( !this[1] )
    result = CGroupPolicyDatabase::Bind((CGroupPolicyDatabase *)(this + 6), this[2], v3);
  if ( *v3 )
  {
    *a2 = *v3;
    return 1;
  }
  else if ( result < 0 )
  {
    if ( *((_DWORD *)this + 8) )
    {
      v6 = (int *)this[5];
      if ( v6 )
        *v6 = result;
    }
    *((_DWORD *)this + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180029540  mov     [rsp+arg_0], rbx
0x180029545  mov     [rsp+arg_8], rsi
0x18002954a  push    rdi
0x18002954b  sub     rsp, 20h
0x18002954f  xor     eax, eax
0x180029551  lea     rdi, [rcx+8]
0x180029555  mov     rsi, rdx
0x180029558  mov     rbx, rcx
0x18002955b  cmp     [rdi], rax
0x18002955e  jnz     short loc_180029570
0x180029560  mov     rdx, [rbx+10h]; unsigned __int16 *
0x180029564  add     rcx, 30h ; '0'; this
0x180029568  mov     r8, rdi; struct IWbemServices **
0x18002956b  call    ?Bind@CGroupPolicyDatabase@@QEAAJPEBGPEAPEAUIWbemServices@@@Z; CGroupPolicyDatabase::Bind(ushort const *,IWbemServices * *)
0x180029570  mov     rcx, [rdi]
0x180029573  test    rcx, rcx
0x180029576  jz      short loc_180029582
0x180029578  mov     [rsi], rcx
0x18002957b  mov     eax, 1
0x180029580  jmp     short loc_18002959E
0x180029582  test    eax, eax
0x180029584  jns     short loc_18002959E
0x180029586  cmp     dword ptr [rbx+20h], 0
0x18002958a  jz      short loc_180029597
0x18002958c  mov     rcx, [rbx+28h]
0x180029590  test    rcx, rcx
0x180029593  jz      short loc_180029597
0x180029595  mov     [rcx], eax
0x180029597  mov     dword ptr [rbx+20h], 0
0x18002959e  mov     rbx, [rsp+28h+arg_0]
0x1800295a3  mov     rsi, [rsp+28h+arg_8]
0x1800295a8  add     rsp, 20h
0x1800295ac  pop     rdi
0x1800295ad  retn
```

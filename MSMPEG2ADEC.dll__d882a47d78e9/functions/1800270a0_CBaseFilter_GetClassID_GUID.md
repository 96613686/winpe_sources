# CBaseFilter::GetClassID(_GUID *)

- ea: `0x1800270a0`
- end: `0x1800270b7`
- name: `?GetClassID@CBaseFilter@@UEAAJPEAU_GUID@@@Z`
- size: `23`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800270a0`

## pseudocode

```c
__int64 __fastcall CBaseFilter::GetClassID(CBaseFilter *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = *(struct _GUID *)((char *)this + 40);
  return result;
}

```

## disassembly

```asm
0x1800270a0  test    rdx, rdx
0x1800270a3  jnz     short loc_1800270AC
0x1800270a5  mov     eax, 80004003h
0x1800270aa  retn
0x1800270ac  movups  xmm0, xmmword ptr [rcx+28h]
0x1800270b0  xor     eax, eax
0x1800270b2  movdqu  xmmword ptr [rdx], xmm0
0x1800270b6  retn
```

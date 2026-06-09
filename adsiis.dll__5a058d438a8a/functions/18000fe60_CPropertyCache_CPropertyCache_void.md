# CPropertyCache::CPropertyCache(void)

- ea: `0x18000fe60`
- end: `0x18000fee2`
- name: `??0CPropertyCache@@QEAA@XZ`
- size: `130`
- prototype: `CPropertyCache *__fastcall(CPropertyCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010a74`

## callees

- `0x180019504`
- `0x18001984c`

## pseudocode

```c
CPropertyCache *__fastcall CPropertyCache::CPropertyCache(CPropertyCache *this, struct WIN32_CRITSEC *a2)
{
  CPropertyCache *result; // rax

  *(_QWORD *)this = &IPropertyCache::`vftable';
  SERVER_CACHE::ReferenceGlobalCache((__int64)this, a2);
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CPropertyCache::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  CCredentials::Initialize((CPropertyCache *)((char *)this + 48), 0, 0, 0);
  result = this;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x18000fe60  push    rbx
0x18000fe62  sub     rsp, 20h
0x18000fe66  lea     rax, ??_7IPropertyCache@@6B@; const IPropertyCache::`vftable'
0x18000fe6d  mov     rbx, rcx
0x18000fe70  mov     [rcx], rax
0x18000fe73  call    ?ReferenceGlobalCache@SERVER_CACHE@@SAXXZ; SERVER_CACHE::ReferenceGlobalCache(void)
0x18000fe78  lea     rax, ??_7CPropertyCache@@6B@; const CPropertyCache::`vftable'
0x18000fe7f  mov     dword ptr [rbx+8], 0
0x18000fe86  lea     rcx, [rbx+30h]; this
0x18000fe8a  mov     [rbx], rax
0x18000fe8d  xor     r9d, r9d; unsigned int
0x18000fe90  mov     qword ptr [rbx+10h], 0
0x18000fe98  xor     r8d, r8d; unsigned __int16 *
0x18000fe9b  mov     dword ptr [rbx+18h], 0
0x18000fea2  xor     edx, edx; unsigned __int16 *
0x18000fea4  mov     qword ptr [rbx+20h], 0
0x18000feac  mov     qword ptr [rbx+28h], 0
0x18000feb4  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x18000feb9  mov     rax, rbx
0x18000febc  mov     qword ptr [rbx+48h], 0
0x18000fec4  mov     qword ptr [rbx+50h], 0
0x18000fecc  mov     qword ptr [rbx+58h], 0
0x18000fed4  mov     qword ptr [rbx+60h], 0
0x18000fedc  add     rsp, 20h
0x18000fee0  pop     rbx
0x18000fee1  retn
```

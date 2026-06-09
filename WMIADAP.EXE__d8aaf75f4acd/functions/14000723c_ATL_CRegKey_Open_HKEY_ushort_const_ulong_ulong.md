# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)

- ea: `0x14000723c`
- end: `0x14000728e`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z`
- size: `82`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY, const unsigned __int16 *, REGSAM)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140006df0`
- `0x14000735c`
- `0x1400073fc`
- `0x1400083dc`

## callees

- `0x140006a78`
- `0x14000723c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007268`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007268`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, a4, &v7);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = v7;
  }
  return v5;
}

```

## disassembly

```asm
0x14000723c  mov     rax, rsp
0x14000723f  mov     [rax+10h], rdx
0x140007243  push    rbx
0x140007244  sub     rsp, 30h
0x140007248  mov     rbx, rcx
0x14000724b  mov     qword ptr [rax+10h], 0
0x140007253  lea     rcx, [rax+10h]
0x140007257  mov     rdx, r8; lpSubKey
0x14000725a  mov     [rax-18h], rcx
0x14000725e  xor     r8d, r8d; ulOptions
0x140007261  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140007268  call    cs:__imp_RegOpenKeyExW
0x14000726e  mov     edx, eax
0x140007270  test    eax, eax
0x140007272  jnz     short loc_140007286
0x140007274  mov     rcx, rbx; this
0x140007277  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000727c  mov     edx, eax
0x14000727e  mov     rax, [rsp+38h+arg_8]
0x140007283  mov     [rbx], rax
0x140007286  mov     eax, edx
0x140007288  add     rsp, 30h
0x14000728c  pop     rbx
0x14000728d  retn
```

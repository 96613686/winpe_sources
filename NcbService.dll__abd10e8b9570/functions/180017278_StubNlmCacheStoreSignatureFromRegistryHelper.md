# StubNlmCacheStoreSignatureFromRegistryHelper

- ea: `0x180017278`
- end: `0x1800173bb`
- name: `StubNlmCacheStoreSignatureFromRegistryHelper`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016f40`

## callees

- `0x180017278`
- `0x18001c500`
- `0x18001d09c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800172e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001734a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800172e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001734a`

## pseudocode

```c
unsigned int __fastcall StubNlmCacheStoreSignatureFromRegistryHelper(__int64 a1, HKEY a2, __int64 a3)
{
  unsigned int v5; // eax
  PVOID *v6; // rcx
  unsigned int result; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  v5 = RegSetValueExW(a2, L"NumNetworks", 0, 4u, (const BYTE *)(a3 + 16), 4u);
  if ( !v5 )
    goto LABEL_10;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, v5);
LABEL_10:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  result = *(_DWORD *)(a3 + 16);
  if ( result )
  {
    result = RegSetValueExW(a2, L"Networks", 0, 3u, *(const BYTE **)(a3 + 8), 16 * result);
    if ( !result )
    {
LABEL_17:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return result;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      result = WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 174,
                 &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids,
                 result);
      goto LABEL_17;
    }
  }
LABEL_18:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    return WPP_SF_(v6[2], 175, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180017278  push    rbx
0x18001727a  push    rsi
0x18001727b  push    rdi
0x18001727c  push    r14
0x18001727e  sub     rsp, 38h
0x180017282  mov     rdi, r8
0x180017285  mov     rsi, rdx
0x180017288  mov     rcx, cs:WPP_GLOBAL_Control
0x18001728f  lea     r14, WPP_GLOBAL_Control
0x180017296  cmp     rcx, r14
0x180017299  jz      short loc_1800172BC
0x18001729b  test    byte ptr [rcx+1Ch], 4
0x18001729f  jz      short loc_1800172BC
0x1800172a1  cmp     byte ptr [rcx+19h], 6
0x1800172a5  jb      short loc_1800172BC
0x1800172a7  mov     rcx, [rcx+10h]
0x1800172ab  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x1800172b2  mov     edx, 0ACh
0x1800172b7  call    WPP_SF_
0x1800172bc  lea     rbx, [rdi+10h]
0x1800172c0  mov     [rsp+58h+cbData], 4; cbData
0x1800172c8  mov     r9d, 4; dwType
0x1800172ce  mov     [rsp+58h+lpData], rbx; lpData
0x1800172d3  xor     r8d, r8d; Reserved
0x1800172d6  lea     rdx, aNumnetworks; "NumNetworks"
0x1800172dd  mov     rcx, rsi; hKey
0x1800172e0  call    cs:__imp_RegSetValueExW
0x1800172e6  test    eax, eax
0x1800172e8  jz      short loc_18001731A
0x1800172ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172f1  cmp     rcx, r14
0x1800172f4  jz      short loc_180017321
0x1800172f6  test    byte ptr [rcx+1Ch], 4
0x1800172fa  jz      short loc_180017321
0x1800172fc  cmp     byte ptr [rcx+19h], 3
0x180017300  jb      short loc_180017321
0x180017302  mov     rcx, [rcx+10h]
0x180017306  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18001730d  mov     edx, 0ADh
0x180017312  mov     r9d, eax
0x180017315  call    WPP_SF_d
0x18001731a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017321  mov     eax, [rbx]
0x180017323  test    eax, eax
0x180017325  jz      short loc_18001738B
0x180017327  shl     eax, 4
0x18001732a  lea     rdx, aNetworks; "Networks"
0x180017331  mov     [rsp+58h+cbData], eax; cbData
0x180017335  mov     r9d, 3; dwType
0x18001733b  mov     rax, [rdi+8]
0x18001733f  xor     r8d, r8d; Reserved
0x180017342  mov     rcx, rsi; hKey
0x180017345  mov     [rsp+58h+lpData], rax; lpData
0x18001734a  call    cs:__imp_RegSetValueExW
0x180017350  test    eax, eax
0x180017352  jz      short loc_180017384
0x180017354  mov     rcx, cs:WPP_GLOBAL_Control
0x18001735b  cmp     rcx, r14
0x18001735e  jz      short loc_1800173B1
0x180017360  test    byte ptr [rcx+1Ch], 4
0x180017364  jz      short loc_18001738B
0x180017366  cmp     byte ptr [rcx+19h], 3
0x18001736a  jb      short loc_18001738B
0x18001736c  mov     rcx, [rcx+10h]
0x180017370  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180017377  mov     edx, 0AEh
0x18001737c  mov     r9d, eax
0x18001737f  call    WPP_SF_d
0x180017384  mov     rcx, cs:WPP_GLOBAL_Control
0x18001738b  cmp     rcx, r14
0x18001738e  jz      short loc_1800173B1
0x180017390  test    byte ptr [rcx+1Ch], 4
0x180017394  jz      short loc_1800173B1
0x180017396  cmp     byte ptr [rcx+19h], 6
0x18001739a  jb      short loc_1800173B1
0x18001739c  mov     rcx, [rcx+10h]
0x1800173a0  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x1800173a7  mov     edx, 0AFh
0x1800173ac  call    WPP_SF_
0x1800173b1  add     rsp, 38h
0x1800173b5  pop     r14
0x1800173b7  pop     rdi
0x1800173b8  pop     rsi
0x1800173b9  pop     rbx
0x1800173ba  retn
```

# ConsoleCreateObject

- ea: `0x14001e7d4`
- end: `0x14001e8e2`
- name: `ConsoleCreateObject`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001f0e0`

## callees

- `0x14001e7d4`
- `0x14001ef70`
- `0x14001f07c`
- `0x14001f40c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001e879`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001e8d3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001e879`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001e8d3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001e826`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001e826`

## pseudocode

```c
__int64 __fastcall ConsoleCreateObject(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rbp
  __int64 v4; // rdi
  int v5; // edi
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 result; // rax
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 352) == 4 )
  {
    v2 = *(_DWORD *)(a1 + 360) & 0xC0000000;
    if ( v2 == 0x80000000 )
    {
      *(_DWORD *)(a1 + 352) = 1;
    }
    else if ( v2 == 0x40000000 )
    {
      *(_DWORD *)(a1 + 352) = 2;
    }
  }
  v3 = a1 + 48;
  v4 = 0;
  v10 = 0;
  RtlAcquireSRWLockExclusive(a1 + 48);
  if ( *(_DWORD *)(a1 + 352) == 1 )
  {
    v6 = 0;
LABEL_17:
    v7 = 0;
    goto LABEL_18;
  }
  if ( *(_DWORD *)(a1 + 352) == 2 )
  {
    v8 = *(_QWORD *)(a1 + 96);
    if ( !v8 )
    {
      v5 = -1073741275;
      goto LABEL_14;
    }
    ++*(_DWORD *)(v8 + 16);
    v6 = *(_QWORD *)(a1 + 96);
    goto LABEL_17;
  }
  if ( *(_DWORD *)(a1 + 352) != 3 )
  {
    v5 = -1073741811;
LABEL_14:
    result = RtlReleaseSRWLockExclusive(v3);
    *(_DWORD *)(a1 + 224) = v5;
    return result;
  }
  v5 = CspAllocateServerScreen(&v10, a1);
  if ( v5 < 0 )
    goto LABEL_14;
  v4 = v10;
  v6 = v10;
  v7 = v10;
LABEL_18:
  *(_QWORD *)(a1 + 208) = 0;
  *(_DWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = v6;
  if ( (int)CspCompleteConsoleIo(a1, a1 + 216) < 0 )
  {
    if ( v7 )
      CspFreeServerScreen(v4);
  }
  return RtlReleaseSRWLockExclusive(v3);
}

```

## disassembly

```asm
0x14001e7d4  push    rbx
0x14001e7d6  push    rbp
0x14001e7d7  push    rsi
0x14001e7d8  push    rdi
0x14001e7d9  sub     rsp, 28h
0x14001e7dd  cmp     dword ptr [rcx+160h], 4
0x14001e7e4  mov     rbx, rcx
0x14001e7e7  jnz     short loc_14001E818
0x14001e7e9  mov     eax, [rcx+168h]
0x14001e7ef  and     eax, 0C0000000h
0x14001e7f4  cmp     eax, 80000000h
0x14001e7f9  jnz     short loc_14001E807
0x14001e7fb  mov     dword ptr [rcx+160h], 1
0x14001e805  jmp     short loc_14001E818
0x14001e807  cmp     eax, 40000000h
0x14001e80c  jnz     short loc_14001E818
0x14001e80e  mov     dword ptr [rcx+160h], 2
0x14001e818  lea     rbp, [rcx+30h]
0x14001e81c  xor     edi, edi
0x14001e81e  mov     rcx, rbp
0x14001e821  mov     [rsp+48h+arg_0], rdi
0x14001e826  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001e82c  mov     ecx, [rbx+160h]
0x14001e832  sub     ecx, 1
0x14001e835  jz      short loc_14001E890
0x14001e837  sub     ecx, 1
0x14001e83a  jz      short loc_14001E868
0x14001e83c  cmp     ecx, 1
0x14001e83f  jz      short loc_14001E848
0x14001e841  mov     edi, 0C000000Dh
0x14001e846  jmp     short loc_14001E876
0x14001e848  mov     rdx, rbx
0x14001e84b  lea     rcx, [rsp+48h+arg_0]
0x14001e850  call    CspAllocateServerScreen
0x14001e855  mov     edi, eax
0x14001e857  test    eax, eax
0x14001e859  js      short loc_14001E876
0x14001e85b  mov     rdi, [rsp+48h+arg_0]
0x14001e860  mov     rax, rdi
0x14001e863  mov     rsi, rdi
0x14001e866  jmp     short loc_14001E894
0x14001e868  mov     rax, [rbx+60h]
0x14001e86c  test    rax, rax
0x14001e86f  jnz     short loc_14001E887
0x14001e871  mov     edi, 0C0000225h
0x14001e876  mov     rcx, rbp
0x14001e879  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001e87f  mov     [rbx+0E0h], edi
0x14001e885  jmp     short loc_14001E8D9
0x14001e887  inc     dword ptr [rax+10h]
0x14001e88a  mov     rax, [rbx+60h]
0x14001e88e  jmp     short loc_14001E892
0x14001e890  xor     eax, eax
0x14001e892  xor     esi, esi
0x14001e894  lea     rdx, [rbx+0D8h]
0x14001e89b  mov     qword ptr [rbx+0D0h], 0
0x14001e8a6  mov     rcx, rbx
0x14001e8a9  mov     dword ptr [rbx+0E0h], 0
0x14001e8b3  mov     [rbx+0E8h], rax
0x14001e8ba  call    CspCompleteConsoleIo
0x14001e8bf  test    eax, eax
0x14001e8c1  jns     short loc_14001E8D0
0x14001e8c3  test    rsi, rsi
0x14001e8c6  jz      short loc_14001E8D0
0x14001e8c8  mov     rcx, rdi
0x14001e8cb  call    CspFreeServerScreen
0x14001e8d0  mov     rcx, rbp
0x14001e8d3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001e8d9  add     rsp, 28h
0x14001e8dd  pop     rdi
0x14001e8de  pop     rsi
0x14001e8df  pop     rbp
0x14001e8e0  pop     rbx
0x14001e8e1  retn
```

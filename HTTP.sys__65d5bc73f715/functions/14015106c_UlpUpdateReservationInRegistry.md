# UlpUpdateReservationInRegistry

- ea: `0x14015106c`
- end: `0x140151257`
- name: `UlpUpdateReservationInRegistry`
- size: `491`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1401503f0`
- `0x1401506e8`

## callees

- `0x140042490`
- `0x14015106c`
- `0x140167940`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x140151211`
- `ntoskrnl!ZwDeleteValueKey` at `0x14015121f`
- `ntoskrnl!ZwDeleteValueKey` at `0x140151211`
- `ntoskrnl!ZwDeleteValueKey` at `0x14015121f`
- `ntoskrnl!ZwSetValueKey` at `0x1401511f3`
- `ntoskrnl!ZwSetValueKey` at `0x1401511f3`
- `ntoskrnl!wcschr` at `0x140151125`
- `ntoskrnl!wcschr` at `0x140151144`
- `ntoskrnl!wcschr` at `0x14015115f`
- `ntoskrnl!wcschr` at `0x14015117f`
- `ntoskrnl!wcschr` at `0x140151125`
- `ntoskrnl!wcschr` at `0x140151144`
- `ntoskrnl!wcschr` at `0x14015115f`
- `ntoskrnl!wcschr` at `0x14015117f`
- `ntoskrnl!ExAllocatePool3` at `0x1401510dc`
- `ntoskrnl!ExAllocatePool3` at `0x1401510dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151237`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151237`

## pseudocode

```c
__int64 __fastcall UlpUpdateReservationInRegistry(__int64 a1, char a2, __int64 a3, void *a4, ULONG DataSize)
{
  NTSTATUS inited; // ebx
  size_t v10; // r14
  wchar_t *Pool3; // rax
  wchar_t *v12; // rdi
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // rsi
  wchar_t *v17; // rax
  wchar_t *v18; // rdx
  void *v19; // rcx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-58h] BYREF

  ValueName = 0;
  if ( !*(_QWORD *)(a1 + 1400) )
    return (unsigned int)-1073741816;
  if ( *(_DWORD *)(a3 + 4) == 2 )
  {
    v10 = 2LL * *(unsigned __int16 *)(a3 + 56) + 2;
    Pool3 = (wchar_t *)ExAllocatePool3(258, v10, 1280666709, UxLowPriorityPool, 1);
    v12 = Pool3;
    if ( !Pool3 )
      return (unsigned int)-1073741670;
    inited = 0;
    memmove(Pool3, *(const void **)(a3 + 8), v10);
    v13 = v12 + 7;
    if ( (v12[7] == 91 || v12[8] == 91) && (v13 = wcschr(v12 + 7, 0x5Du)) == 0
      || (v14 = wcschr(v13, 0x3Au)) == 0
      || (v15 = wcschr(v14 + 1, 0x3Au), (v16 = v15) == 0)
      || (v17 = wcschr(v15, 0x2Fu)) == 0 )
    {
LABEL_23:
      ExFreePoolWithTag(v12, 0);
      return (unsigned int)inited;
    }
    while ( *v17 )
      *v16++ = *v17++;
    *v16 = 0;
    v18 = v12;
  }
  else
  {
    v18 = *(wchar_t **)(a3 + 8);
    v12 = 0;
  }
  inited = UlInitUnicodeStringEx(&ValueName, v18, a3, a4);
  if ( inited >= 0 )
  {
    v19 = *(void **)(a1 + 1400);
    if ( a2 )
    {
      inited = ZwSetValueKey(v19, &ValueName, 0, 3u, a4, DataSize);
      if ( inited < 0 )
        ZwDeleteValueKey(*(HANDLE *)(a1 + 1400), &ValueName);
    }
    else
    {
      inited = ZwDeleteValueKey(v19, &ValueName);
    }
  }
  if ( v12 )
    goto LABEL_23;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14015106c  push    rbx
0x14015106e  push    rbp
0x14015106f  push    rsi
0x140151070  push    rdi
0x140151071  push    r12
0x140151073  push    r13
0x140151075  push    r14
0x140151077  push    r15
0x140151079  sub     rsp, 48h
0x14015107d  xor     r13d, r13d
0x140151080  xorps   xmm0, xmm0
0x140151083  mov     r12, r9
0x140151086  mov     rsi, r8
0x140151089  mov     r15b, dl
0x14015108c  mov     rbp, rcx
0x14015108f  movups  xmmword ptr [rsp+88h+ValueName.Length], xmm0
0x140151094  cmp     [rcx+578h], r13
0x14015109b  jnz     short loc_1401510A7
0x14015109d  mov     ebx, 0C0000008h
0x1401510a2  jmp     loc_140151243
0x1401510a7  cmp     dword ptr [r8+4], 2
0x1401510ac  jnz     loc_1401511B2
0x1401510b2  movzx   eax, word ptr [r8+38h]
0x1401510b7  lea     r9, UxLowPriorityPool
0x1401510be  mov     r8d, 4C556C55h
0x1401510c4  mov     dword ptr [rsp+88h+Data], 1
0x1401510cc  mov     ecx, 102h
0x1401510d1  lea     r14, ds:2[rax*2]
0x1401510d9  mov     rdx, r14
0x1401510dc  call    cs:__imp_ExAllocatePool3
0x1401510e3  nop     dword ptr [rax+rax+00h]
0x1401510e8  mov     rdi, rax
0x1401510eb  test    rax, rax
0x1401510ee  jnz     short loc_1401510FA
0x1401510f0  mov     ebx, 0C000009Ah
0x1401510f5  jmp     loc_140151243
0x1401510fa  mov     rdx, [rsi+8]; Src
0x1401510fe  mov     r8, r14; Size
0x140151101  mov     rcx, rdi; void *
0x140151104  mov     ebx, r13d
0x140151107  call    memmove
0x14015110c  lea     rax, [rdi+0Eh]
0x140151110  cmp     word ptr [rax], 5Bh ; '['
0x140151114  jz      short loc_14015111D
0x140151116  cmp     word ptr [rax+2], 5Bh ; '['
0x14015111b  jnz     short loc_14015113A
0x14015111d  mov     edx, 5Dh ; ']'; Ch
0x140151122  mov     rcx, rax; Str
0x140151125  call    cs:__imp_wcschr
0x14015112c  nop     dword ptr [rax+rax+00h]
0x140151131  test    rax, rax
0x140151134  jz      loc_140151232
0x14015113a  mov     esi, 3Ah ; ':'
0x14015113f  mov     rcx, rax; Str
0x140151142  mov     edx, esi; Ch
0x140151144  call    cs:__imp_wcschr
0x14015114b  nop     dword ptr [rax+rax+00h]
0x140151150  test    rax, rax
0x140151153  jz      loc_140151232
0x140151159  mov     edx, esi; Ch
0x14015115b  lea     rcx, [rax+2]; Str
0x14015115f  call    cs:__imp_wcschr
0x140151166  nop     dword ptr [rax+rax+00h]
0x14015116b  mov     rsi, rax
0x14015116e  test    rax, rax
0x140151171  jz      loc_140151232
0x140151177  mov     edx, 2Fh ; '/'; Ch
0x14015117c  mov     rcx, rax; Str
0x14015117f  call    cs:__imp_wcschr
0x140151186  nop     dword ptr [rax+rax+00h]
0x14015118b  test    rax, rax
0x14015118e  jz      loc_140151232
0x140151194  jmp     short loc_1401511A1
0x140151196  mov     [rsi], cx
0x140151199  lea     rax, [rax+2]
0x14015119d  add     rsi, 2
0x1401511a1  movzx   ecx, word ptr [rax]
0x1401511a4  test    cx, cx
0x1401511a7  jnz     short loc_140151196
0x1401511a9  mov     [rsi], r13w
0x1401511ad  mov     rdx, rdi
0x1401511b0  jmp     short loc_1401511B9
0x1401511b2  mov     rdx, [r8+8]
0x1401511b6  mov     rdi, r13
0x1401511b9  lea     rcx, [rsp+88h+ValueName]
0x1401511be  call    UlInitUnicodeStringEx
0x1401511c3  mov     ebx, eax
0x1401511c5  test    eax, eax
0x1401511c7  js      short loc_14015122D
0x1401511c9  mov     rcx, [rbp+578h]; KeyHandle
0x1401511d0  lea     rdx, [rsp+88h+ValueName]; ValueName
0x1401511d5  test    r15b, r15b
0x1401511d8  jz      short loc_14015121F
0x1401511da  mov     eax, [rsp+88h+arg_20]
0x1401511e1  mov     r9d, 3; Type
0x1401511e7  mov     [rsp+88h+DataSize], eax; DataSize
0x1401511eb  xor     r8d, r8d; TitleIndex
0x1401511ee  mov     [rsp+88h+Data], r12; Data
0x1401511f3  call    cs:__imp_ZwSetValueKey
0x1401511fa  nop     dword ptr [rax+rax+00h]
0x1401511ff  mov     ebx, eax
0x140151201  test    eax, eax
0x140151203  jns     short loc_14015122D
0x140151205  mov     rcx, [rbp+578h]; KeyHandle
0x14015120c  lea     rdx, [rsp+88h+ValueName]; ValueName
0x140151211  call    cs:__imp_ZwDeleteValueKey
0x140151218  nop     dword ptr [rax+rax+00h]
0x14015121d  jmp     short loc_14015122D
0x14015121f  call    cs:__imp_ZwDeleteValueKey
0x140151226  nop     dword ptr [rax+rax+00h]
0x14015122b  mov     ebx, eax
0x14015122d  test    rdi, rdi
0x140151230  jz      short loc_140151243
0x140151232  xor     edx, edx; Tag
0x140151234  mov     rcx, rdi; P
0x140151237  call    cs:__imp_ExFreePoolWithTag
0x14015123e  nop     dword ptr [rax+rax+00h]
0x140151243  mov     eax, ebx
0x140151245  add     rsp, 48h
0x140151249  pop     r15
0x14015124b  pop     r14
0x14015124d  pop     r13
0x14015124f  pop     r12
0x140151251  pop     rdi
0x140151252  pop     rsi
0x140151253  pop     rbp
0x140151254  pop     rbx
0x140151255  retn
```

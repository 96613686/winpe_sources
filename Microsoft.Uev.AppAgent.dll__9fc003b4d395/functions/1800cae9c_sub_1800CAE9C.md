# sub_1800CAE9C

- ea: `0x1800cae9c`
- end: `0x1800cb0b2`
- name: `sub_1800CAE9C`
- size: `534`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `13`
- tags: ``

## callers

- `0x1800c8f08`
- `0x1800cd248`
- `0x1800ce358`
- `0x1800cfdc0`
- `0x1800d157c`

## callees

- `0x1800048f0`
- `0x18001916c`
- `0x18001abf0`
- `0x180020dcc`
- `0x180025918`
- `0x180025a94`
- `0x180028810`
- `0x1800296f8`
- `0x180038800`
- `0x180038b44`
- `0x180087970`
- `0x1800ad1bc`
- `0x1800cae9c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800caed4`
- `KERNEL32!GetCurrentThreadId` at `0x1800caed4`
- `KERNEL32!SetEvent` at `0x1800cb08a`
- `KERNEL32!SetEvent` at `0x1800cb08a`

## string_xrefs

- `0x1800caf72`: `SyncState::GetRestoreCount() -  Error %1% occurred while getting the restore count for template %2%.`

## pseudocode

```c
__int64 __fastcall sub_1800CAE9C(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  DWORD CurrentThreadId; // ebx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  volatile signed __int32 *v6; // r14
  __int64 v7; // rax
  __int64 *v8; // rdi
  __int64 v9; // rcx
  __int64 *v10; // rax
  __int64 *v11; // rax
  __int64 *v12; // rbx
  unsigned int v13; // ebx
  signed __int32 v15; // eax
  HANDLE v16; // rax
  __int128 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v19; // [rsp+30h] [rbp-D0h]
  __int64 v20; // [rsp+40h] [rbp-C0h]
  _OWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[272]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v23; // [rsp+180h] [rbp+80h] BYREF
  __int64 v24; // [rsp+188h] [rbp+88h] BYREF

  v3 = a1 + 656;
  v20 = a1 + 656;
  CurrentThreadId = GetCurrentThreadId();
  v5 = (void (__fastcall ***)(_QWORD, __int64))*(unsigned int *)(v3 + 4);
  v6 = (volatile signed __int32 *)(v3 + 8);
  if ( (_DWORD)v5 == CurrentThreadId )
  {
    ++*(_DWORD *)v3;
  }
  else
  {
    sub_180087970(v3 + 8);
    _InterlockedExchange((volatile __int32 *)(v3 + 4), CurrentThreadId);
    *(_DWORD *)v3 = 1;
  }
  v24 = 0;
  v23 = 0;
  v7 = sub_180025918(v5);
  if ( !(unsigned __int8)sub_1800AD1BC(v7 + 20080, a2, &v23, &v24)
    && (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 1) != 0 )
  {
    v8 = (__int64 *)sub_180025A94();
    sub_180025A94();
    memset(v21, 0, sizeof(v21));
    sub_18001916C(
      v21,
      L"SyncState::GetRestoreCount() -  Error %1% occurred while getting the restore count for template %2%.",
      0x64u);
    v10 = (__int64 *)sub_180038B44(v9, (__int64)v22, (__int64)v21);
    *(_QWORD *)&v18 = &v24;
    *((_QWORD *)&v18 + 1) = guard_check_icall_nop;
    *(_QWORD *)&v19 = sub_18001AB60;
    v11 = sub_18001ABF0(v10, (__int64)&v18);
    *(_QWORD *)&v18 = a2;
    *((_QWORD *)&v18 + 1) = guard_check_icall_nop;
    *(_QWORD *)&v19 = sub_180018450;
    v12 = sub_18001ABF0(v11, (__int64)&v18);
    v18 = 0;
    v19 = 0;
    sub_18001916C(&v18, L"Orchestrator", 0xCu);
    sub_180038800(v8, 1u, (__int64)&v18, (__int64)v12);
    sub_180028810(&v18);
    sub_180020DCC((__int64)v22);
    sub_180028810(v21);
  }
  v13 = v23;
  if ( (*(_DWORD *)v3)-- == 1 )
  {
    _InterlockedExchange((volatile __int32 *)(v3 + 4), 0);
    v15 = _InterlockedExchangeAdd(v6, 0x80000000);
    if ( (v15 & 0x40000000) == 0 && v15 != 0x80000000 && !_interlockedbittestandset(v6, 0x1Eu) )
    {
      v16 = sub_1800296F8(v3 + 8);
      SetEvent(v16);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800cae9c  push    rbp
0x1800cae9e  push    rbx
0x1800cae9f  push    rsi
0x1800caea0  push    rdi
0x1800caea1  push    r14
0x1800caea3  push    r15
0x1800caea5  lea     rbp, [rsp-0A8h]
0x1800caead  sub     rsp, 1A8h
0x1800caeb4  mov     rax, cs:__security_cookie
0x1800caebb  xor     rax, rsp
0x1800caebe  mov     [rbp+0D0h+var_40], rax
0x1800caec5  mov     r15, rdx
0x1800caec8  lea     rsi, [rcx+290h]
0x1800caecf  mov     [rsp+1D0h+var_190], rsi
0x1800caed4  call    cs:GetCurrentThreadId
0x1800caeda  mov     ebx, eax
0x1800caedc  mov     ecx, [rsi+4]
0x1800caedf  nop
0x1800caee0  lea     r14, [rsi+8]
0x1800caee4  cmp     ecx, eax
0x1800caee6  jnz     short loc_1800CAEEC
0x1800caee8  inc     dword ptr [rsi]
0x1800caeea  jmp     short loc_1800CAEFD
0x1800caeec  mov     rcx, r14
0x1800caeef  call    sub_180087970
0x1800caef4  xchg    ebx, [rsi+4]
0x1800caef7  mov     dword ptr [rsi], 1
0x1800caefd  mov     [rbp+0D0h+var_48], 0
0x1800caf08  mov     [rbp+0D0h+var_50], 0
0x1800caf12  call    sub_180025918
0x1800caf17  lea     rcx, [rax+4E70h]
0x1800caf1e  lea     r9, [rbp+0D0h+var_48]
0x1800caf25  lea     r8, [rbp+0D0h+var_50]
0x1800caf2c  mov     rdx, r15
0x1800caf2f  call    sub_1800AD1BC
0x1800caf34  test    al, al
0x1800caf36  jnz     loc_1800CB051
0x1800caf3c  call    sub_180025A94
0x1800caf41  mov     rax, [rax]
0x1800caf44  test    byte ptr [rax+20h], 1
0x1800caf48  jbe     loc_1800CB051
0x1800caf4e  call    sub_180025A94
0x1800caf53  mov     rdi, rax
0x1800caf56  call    sub_180025A94
0x1800caf5b  xorps   xmm0, xmm0
0x1800caf5e  movups  [rsp+1D0h+var_188], xmm0
0x1800caf63  xorps   xmm1, xmm1
0x1800caf66  movdqu  [rsp+1D0h+var_178], xmm1
0x1800caf6c  mov     r8d, 64h ; 'd'
0x1800caf72  lea     rdx, aSyncstateGetre; "SyncState::GetRestoreCount() -  Error %"...
0x1800caf79  lea     rcx, [rsp+1D0h+var_188]
0x1800caf7e  call    sub_18001916C
0x1800caf83  nop
0x1800caf84  lea     r8, [rsp+1D0h+var_188]
0x1800caf89  lea     rdx, [rsp+1D0h+var_160]
0x1800caf8e  call    sub_180038B44
0x1800caf93  nop
0x1800caf94  lea     rcx, [rbp+0D0h+var_48]
0x1800caf9b  mov     qword ptr [rsp+1D0h+var_1B0], rcx
0x1800cafa0  lea     rcx, _guard_check_icall_nop
0x1800cafa7  mov     qword ptr [rsp+1D0h+var_1B0+8], rcx
0x1800cafac  lea     rcx, sub_18001AB60
0x1800cafb3  mov     qword ptr [rsp+1D0h+var_1A0], rcx
0x1800cafb8  lea     rdx, [rsp+1D0h+var_1B0]
0x1800cafbd  mov     rcx, rax
0x1800cafc0  call    sub_18001ABF0
0x1800cafc5  mov     qword ptr [rsp+1D0h+var_1B0], r15
0x1800cafca  lea     rcx, _guard_check_icall_nop
0x1800cafd1  mov     qword ptr [rsp+1D0h+var_1B0+8], rcx
0x1800cafd6  lea     rcx, sub_180018450
0x1800cafdd  mov     qword ptr [rsp+1D0h+var_1A0], rcx
0x1800cafe2  lea     rdx, [rsp+1D0h+var_1B0]
0x1800cafe7  mov     rcx, rax
0x1800cafea  call    sub_18001ABF0
0x1800cafef  mov     rbx, rax
0x1800caff2  xorps   xmm0, xmm0
0x1800caff5  movups  [rsp+1D0h+var_1B0], xmm0
0x1800caffa  xorps   xmm1, xmm1
0x1800caffd  movdqu  [rsp+1D0h+var_1A0], xmm1
0x1800cb003  mov     r8d, 0Ch
0x1800cb009  lea     rdx, aOrchestrator; "Orchestrator"
0x1800cb010  lea     rcx, [rsp+1D0h+var_1B0]
0x1800cb015  call    sub_18001916C
0x1800cb01a  nop
0x1800cb01b  mov     r9, rbx
0x1800cb01e  lea     r8, [rsp+1D0h+var_1B0]
0x1800cb023  mov     edx, 1
0x1800cb028  mov     rcx, rdi
0x1800cb02b  call    sub_180038800
0x1800cb030  nop
0x1800cb031  lea     rcx, [rsp+1D0h+var_1B0]
0x1800cb036  call    sub_180028810
0x1800cb03b  nop
0x1800cb03c  lea     rcx, [rsp+1D0h+var_160]
0x1800cb041  call    sub_180020DCC
0x1800cb046  nop
0x1800cb047  lea     rcx, [rsp+1D0h+var_188]
0x1800cb04c  call    sub_180028810
0x1800cb051  mov     ebx, [rbp+0D0h+var_50]
0x1800cb057  sub     dword ptr [rsi], 1
0x1800cb05a  jnz     short loc_1800CB091
0x1800cb05c  xor     eax, eax
0x1800cb05e  xchg    eax, [rsi+4]
0x1800cb061  mov     ecx, 80000000h
0x1800cb066  mov     eax, ecx
0x1800cb068  lock xadd [r14], eax
0x1800cb06d  bt      eax, 1Eh
0x1800cb071  jb      short loc_1800CB091
0x1800cb073  cmp     eax, ecx
0x1800cb075  jle     short loc_1800CB091
0x1800cb077  lock bts dword ptr [r14], 1Eh
0x1800cb07d  jb      short loc_1800CB091
0x1800cb07f  mov     rcx, r14
0x1800cb082  call    sub_1800296F8
0x1800cb087  mov     rcx, rax; hEvent
0x1800cb08a  call    cs:SetEvent
0x1800cb090  nop
0x1800cb091  mov     eax, ebx
0x1800cb093  mov     rcx, [rbp+0D0h+var_40]
0x1800cb09a  xor     rcx, rsp; StackCookie
0x1800cb09d  call    __security_check_cookie
0x1800cb0a2  add     rsp, 1A8h
0x1800cb0a9  pop     r15
0x1800cb0ab  pop     r14
0x1800cb0ad  pop     rdi
0x1800cb0ae  pop     rsi
0x1800cb0af  pop     rbx
0x1800cb0b0  pop     rbp
0x1800cb0b1  retn
```

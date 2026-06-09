# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180002a14`
- end: `0x180002ad8`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `196`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002a00`
- `0x180004f00`
- `0x180006180`
- `0x180006e10`
- `0x180008040`
- `0x1800093b0`
- `0x1800097d0`

## callees

- `0x180002a14`
- `0x180002ae0`
- `0x1800040dc`
- `0x180013056`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        LCID lcid,
        int *a6)
{
  __int64 result; // rax
  __int64 v10; // r14
  __int64 v11; // rsi
  int v12; // eax
  int v13; // ebx
  int v14; // r12d

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    result = 0;
  else
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 5);
    if ( v11 && a4 == 1 )
    {
      v12 = ocslen(*a3);
      v13 = *((_DWORD *)this + 12);
      v14 = v12;
      while ( --v13 >= 0 )
      {
        if ( v14 == *(_DWORD *)(v11 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v11 + 16LL * v13), *a3, 2LL * *(int *)(v11 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v11 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **, _QWORD, int *))(*(_QWORD *)v10 + 80LL))(
             v10,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x180002a14  push    rbx
0x180002a16  push    rbp
0x180002a17  push    rsi
0x180002a18  push    rdi
0x180002a19  push    r12
0x180002a1b  push    r14
0x180002a1d  push    r15
0x180002a1f  sub     rsp, 30h
0x180002a23  cmp     qword ptr [rcx+18h], 0
0x180002a28  mov     ebp, r9d
0x180002a2b  mov     r15, r8
0x180002a2e  mov     rdi, rcx
0x180002a31  jz      short loc_180002A3E
0x180002a33  cmp     qword ptr [rcx+28h], 0
0x180002a38  jz      short loc_180002A3E
0x180002a3a  xor     eax, eax
0x180002a3c  jmp     short loc_180002A4A
0x180002a3e  mov     edx, [rsp+68h+lcid]; lcid
0x180002a45  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180002a4a  mov     r14, [rdi+18h]
0x180002a4e  test    r14, r14
0x180002a51  jz      short loc_180002AC9
0x180002a53  mov     rsi, [rdi+28h]
0x180002a57  test    rsi, rsi
0x180002a5a  jz      short loc_180002AAC
0x180002a5c  cmp     ebp, 1
0x180002a5f  jnz     short loc_180002AAC
0x180002a61  mov     rcx, [r15]; unsigned __int16 *
0x180002a64  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180002a69  mov     ebx, [rdi+30h]
0x180002a6c  mov     r12d, eax
0x180002a6f  dec     ebx
0x180002a71  test    ebx, ebx
0x180002a73  js      short loc_180002AAC
0x180002a75  movsxd  rdi, ebx
0x180002a78  add     rdi, rdi
0x180002a7b  cmp     r12d, [rsi+rdi*8+8]
0x180002a80  jnz     short loc_180002A6F
0x180002a82  movsxd  r8, dword ptr [rsi+rdi*8+8]
0x180002a87  mov     rdx, [r15]; Buf2
0x180002a8a  add     r8, r8; Size
0x180002a8d  mov     rcx, [rsi+rdi*8]; Buf1
0x180002a91  call    memcmp_0
0x180002a96  test    eax, eax
0x180002a98  jnz     short loc_180002A6F
0x180002a9a  mov     rax, [rsp+68h+arg_28]
0x180002aa2  mov     ecx, [rsi+rdi*8+0Ch]
0x180002aa6  mov     [rax], ecx
0x180002aa8  xor     eax, eax
0x180002aaa  jmp     short loc_180002AC9
0x180002aac  mov     rax, [r14]
0x180002aaf  mov     r8d, ebp
0x180002ab2  mov     r9, [rsp+68h+arg_28]
0x180002aba  mov     rdx, r15
0x180002abd  mov     rcx, r14
0x180002ac0  mov     rax, [rax+50h]
0x180002ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac9  add     rsp, 30h
0x180002acd  pop     r15
0x180002acf  pop     r14
0x180002ad1  pop     r12
0x180002ad3  pop     rdi
0x180002ad4  pop     rsi
0x180002ad5  pop     rbp
0x180002ad6  pop     rbx
0x180002ad7  retn
```

# CommonUtil::CreateNewRefObject<MpConfigUtils::CSimpleMpConfig>(MpConfigUtils::CSimpleMpConfig * *)

- ea: `0x180005f88`
- end: `0x180005ff8`
- name: `??$CreateNewRefObject@VCSimpleMpConfig@MpConfigUtils@@@CommonUtil@@YAJPEAPEAVCSimpleMpConfig@MpConfigUtils@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004ccc`

## callees

- `0x180002188`
- `0x180005f88`

## pseudocode

```c
__int64 __fastcall CommonUtil::CreateNewRefObject<MpConfigUtils::CSimpleMpConfig>(_QWORD *a1)
{
  void *v2; // rdx

  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  *((_DWORD *)v2 + 2) = 0;
  *(_QWORD *)v2 = &MpConfigUtils::CSimpleMpConfig::`vftable';
  *((_DWORD *)v2 + 7) = 252844334;
  *((_QWORD *)v2 + 7) = 0;
  if ( *((_DWORD *)v2 + 2) )
    _InterlockedIncrement((volatile signed __int32 *)v2 + 2);
  else
    *((_DWORD *)v2 + 2) = 1;
  *a1 = v2;
  return 0;
}

```

## disassembly

```asm
0x180005f88  push    rbx
0x180005f8a  sub     rsp, 30h
0x180005f8e  mov     rbx, rcx
0x180005f91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005f98  mov     ecx, 40h ; '@'; unsigned __int64
0x180005f9d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005fa2  mov     rdx, rax
0x180005fa5  xor     eax, eax
0x180005fa7  test    rdx, rdx
0x180005faa  jz      short loc_180005FDF
0x180005fac  mov     [rdx+8], eax
0x180005faf  lea     rcx, ??_7CSimpleMpConfig@MpConfigUtils@@6B@; const MpConfigUtils::CSimpleMpConfig::`vftable'
0x180005fb6  mov     [rdx], rcx
0x180005fb9  mov     dword ptr [rdx+1Ch], 0F12192Eh
0x180005fc0  mov     [rdx+38h], rax
0x180005fc4  mov     ecx, [rdx+8]
0x180005fc7  test    ecx, ecx
0x180005fc9  jnz     short loc_180005FD4
0x180005fcb  mov     dword ptr [rdx+8], 1
0x180005fd2  jmp     short loc_180005FD8
0x180005fd4  lock inc dword ptr [rdx+8]
0x180005fd8  mov     [rbx], rdx
0x180005fdb  xor     eax, eax
0x180005fdd  jmp     short loc_180005FF1
0x180005fdf  mov     eax, 8007000Eh
0x180005fe4  jmp     short loc_180005FF1
0x180005fe6  xor     eax, eax
0x180005fe8  cmp     [rsp+38h+arg_8], eax
0x180005fec  cmovl   eax, [rsp+38h+arg_10]
0x180005ff1  add     rsp, 30h
0x180005ff5  pop     rbx
0x180005ff6  retn
```

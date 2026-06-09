# CommonUtil::CreateNewRefObject<MpConfigUtils::CRefCachedConfigKey>(MpConfigUtils::CRefCachedConfigKey * *)

- ea: `0x180005f14`
- end: `0x180005f81`
- name: `??$CreateNewRefObject@VCRefCachedConfigKey@MpConfigUtils@@@CommonUtil@@YAJPEAPEAVCRefCachedConfigKey@MpConfigUtils@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000627c`

## callees

- `0x180002188`
- `0x180005f14`

## pseudocode

```c
__int64 __fastcall CommonUtil::CreateNewRefObject<MpConfigUtils::CRefCachedConfigKey>(_QWORD *a1)
{
  void *v2; // rdx

  v2 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  *((_DWORD *)v2 + 2) = 0;
  *(_QWORD *)v2 = &MpConfigUtils::CRefCachedConfigKey::`vftable';
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
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
0x180005f14  push    rbx
0x180005f16  sub     rsp, 30h
0x180005f1a  mov     rbx, rcx
0x180005f1d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005f24  mov     ecx, 20h ; ' '; unsigned __int64
0x180005f29  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005f2e  mov     rdx, rax
0x180005f31  xor     eax, eax
0x180005f33  test    rdx, rdx
0x180005f36  jz      short loc_180005F68
0x180005f38  mov     [rdx+8], eax
0x180005f3b  lea     rcx, ??_7CRefCachedConfigKey@MpConfigUtils@@6B@; const MpConfigUtils::CRefCachedConfigKey::`vftable'
0x180005f42  mov     [rdx], rcx
0x180005f45  mov     [rdx+10h], rax
0x180005f49  mov     [rdx+18h], rax
0x180005f4d  mov     ecx, [rdx+8]
0x180005f50  test    ecx, ecx
0x180005f52  jnz     short loc_180005F5D
0x180005f54  mov     dword ptr [rdx+8], 1
0x180005f5b  jmp     short loc_180005F61
0x180005f5d  lock inc dword ptr [rdx+8]
0x180005f61  mov     [rbx], rdx
0x180005f64  xor     eax, eax
0x180005f66  jmp     short loc_180005F7A
0x180005f68  mov     eax, 8007000Eh
0x180005f6d  jmp     short loc_180005F7A
0x180005f6f  xor     eax, eax
0x180005f71  cmp     [rsp+38h+arg_8], eax
0x180005f75  cmovl   eax, [rsp+38h+arg_10]
0x180005f7a  add     rsp, 30h
0x180005f7e  pop     rbx
0x180005f7f  retn
```

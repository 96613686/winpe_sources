# MpConfigUtils::CSimpleMpConfig::~CSimpleMpConfig(void)

- ea: `0x180006020`
- end: `0x18000608b`
- name: `??1CSimpleMpConfig@MpConfigUtils@@UEAA@XZ`
- size: `107`
- prototype: `void __fastcall(MpConfigUtils::CSimpleMpConfig *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006130`

## callees

- `0x180006020`
- `0x18000a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180006075`
- `KERNEL32!DeleteCriticalSection` at `0x180006075`

## pseudocode

```c
void __fastcall MpConfigUtils::CSimpleMpConfig::~CSimpleMpConfig(MpConfigUtils::CSimpleMpConfig *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &MpConfigUtils::CSimpleMpConfig::`vftable';
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    if ( *(_DWORD *)(v2 + 8) == 1 )
    {
      *(_DWORD *)(v2 + 8) = 0;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) > 1 )
    {
      goto LABEL_6;
    }
    (**(void (__fastcall ***)(__int64))v2)(v2);
  }
LABEL_6:
  if ( *((_DWORD *)this + 7) != 252844334 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &CommonUtil::CRefObject::`vftable';
}

```

## disassembly

```asm
0x180006020  push    rbx
0x180006022  sub     rsp, 20h
0x180006026  lea     rax, ??_7CSimpleMpConfig@MpConfigUtils@@6B@; const MpConfigUtils::CSimpleMpConfig::`vftable'
0x18000602d  mov     rbx, rcx
0x180006030  mov     [rcx], rax
0x180006033  mov     rcx, [rcx+38h]
0x180006037  test    rcx, rcx
0x18000603a  jz      short loc_180006068
0x18000603c  mov     eax, [rcx+8]
0x18000603f  mov     edx, 1
0x180006044  cmp     eax, edx
0x180006046  jnz     short loc_180006051
0x180006048  mov     dword ptr [rcx+8], 0
0x18000604f  jmp     short loc_18000605D
0x180006051  or      eax, 0FFFFFFFFh
0x180006054  lock xadd [rcx+8], eax
0x180006059  sub     eax, edx
0x18000605b  jg      short loc_180006068
0x18000605d  mov     rax, [rcx]
0x180006060  mov     rax, [rax]
0x180006063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006068  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000606c  cmp     dword ptr [rcx+0Ch], 0F12192Eh
0x180006073  jz      short loc_18000607B
0x180006075  call    cs:__imp_DeleteCriticalSection
0x18000607b  lea     rax, ??_7CRefObject@CommonUtil@@6B@; const CommonUtil::CRefObject::`vftable'
0x180006082  mov     [rbx], rax
0x180006085  add     rsp, 20h
0x180006089  pop     rbx
0x18000608a  retn
```

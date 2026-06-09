# errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)

- ea: `0x140008454`
- end: `0x140008477`
- name: `??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x140006164`
- `0x140006298`
- `0x14000641c`
- `0x1400076e8`
- `0x140008380`
- `0x140008728`
- `0x140008784`
- `0x140009434`
- `0x1400098b0`
- `0x140009dd8`
- `0x140009e94`
- `0x140009fa4`
- `0x14000a388`
- `0x14000a75c`
- `0x14000ded8`
- `0x14000e510`
- `0x14000e62c`
- `0x14000f54c`
- `0x14001199a`
- `0x140011c59`
- `0x140011d31`
- `0x140011d67`
- `0x140011dd2`
- `0x140011e3e`
- `0x14001207c`
- `0x1400120a0`
- `0x14001213c`
- `0x140012188`

## callees

- `0x140008454`
- `0x140009f58`

## pseudocode

```c
void __fastcall errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(
        __int64 a1,
        unsigned int a2)
{
  int v2; // eax

  v2 = *(_DWORD *)(a1 + 4);
  if ( v2 != 1 && (unsigned int)(v2 - 3) > 3 )
    TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, a2);
}

```

## disassembly

```asm
0x140008454  sub     rsp, 28h
0x140008458  mov     eax, [rcx+4]
0x14000845b  cmp     eax, 1
0x14000845e  jz      short loc_140008472
0x140008460  add     eax, 0FFFFFFFDh
0x140008463  cmp     eax, 3
0x140008466  jbe     short loc_140008472
0x140008468  mov     ecx, 80004004h; this
0x14000846d  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140008472  add     rsp, 28h
0x140008476  retn
```

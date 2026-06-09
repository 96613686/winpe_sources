# CGuard<CMTALock>::~CGuard<CMTALock>(void)

- ea: `0x18000f1d0`
- end: `0x18000f1fd`
- name: `??1?$CGuard@VCMTALock@@@@QEAA@XZ`
- size: `45`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `88`
- callee_count: `2`
- tags: ``

## callers

- `0x1800180a0`
- `0x180019bc0`
- `0x18001a190`
- `0x18001a3a0`
- `0x18001a730`
- `0x18001da20`
- `0x18001dac0`
- `0x18001db10`
- `0x18001e5b0`
- `0x18001efc0`
- `0x18001f080`
- `0x18001f370`
- `0x18001f510`
- `0x18001fd80`
- `0x180020460`
- `0x1800204f0`
- `0x1800206d0`
- `0x1800207a0`
- `0x180020860`
- `0x180020964`
- `0x180020f20`
- `0x180020f70`
- `0x180020ff0`
- `0x180023610`
- `0x180023680`
- `0x1800236f0`
- `0x180023850`
- `0x180023ae0`
- `0x180023bc0`
- `0x180023c10`
- `0x180023d10`
- `0x18002a3f0`
- `0x18002a4a0`
- `0x18002a520`
- `0x18002a720`
- `0x18002a7d0`
- `0x18002a890`
- `0x18002a940`
- `0x18002aae0`
- `0x18002ab70`
- `0x18002ac30`
- `0x18002acd0`
- `0x18002ad70`
- `0x18002b140`
- `0x18002b1e0`
- `0x18002b290`
- `0x18002b310`
- `0x18002b390`
- `0x18002be80`
- `0x18002bf90`

## callees

- `0x18000f1d0`
- `0x180022650`

## pseudocode

```c
void __fastcall CGuard<CMTALock>::~CGuard<CMTALock>(__int64 *a1)
{
  __int64 v1; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( *(_BYTE *)(v1 + 48) )
      LeaveCriticalSection_0((LPCRITICAL_SECTION)(v1 + 8));
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000f1d0  push    rbx
0x18000f1d2  sub     rsp, 20h
0x18000f1d6  mov     rax, [rcx]
0x18000f1d9  mov     rbx, rcx
0x18000f1dc  test    rax, rax
0x18000f1df  jz      short loc_18000F1F7
0x18000f1e1  cmp     byte ptr [rax+30h], 0
0x18000f1e5  lea     rcx, [rax+8]; lpCriticalSection
0x18000f1e9  jz      short loc_18000F1F0
0x18000f1eb  call    LeaveCriticalSection_0
0x18000f1f0  mov     qword ptr [rbx], 0
0x18000f1f7  add     rsp, 20h
0x18000f1fb  pop     rbx
0x18000f1fc  retn
```

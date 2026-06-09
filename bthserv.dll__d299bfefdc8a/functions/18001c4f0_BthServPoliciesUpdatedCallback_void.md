# BthServPoliciesUpdatedCallback(void *)

- ea: `0x18001c4f0`
- end: `0x18001c52b`
- name: `?BthServPoliciesUpdatedCallback@@YAXPEAX@Z`
- size: `59`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001c4f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c520`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c520`

## pseudocode

```c
void __fastcall BthServPoliciesUpdatedCallback(void *a1)
{
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  pftDueTime = (struct _FILETIME)-1000000LL;
  if ( !byte_180044BE8 )
  {
    byte_180044BE8 = 1;
    SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x18001c4f0  sub     rsp, 28h
0x18001c4f4  mov     al, cs:byte_180044BE8
0x18001c4fa  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFF0BDC0h
0x18001c503  test    al, al
0x18001c505  jnz     short loc_18001C526
0x18001c507  mov     rcx, cs:pti; pti
0x18001c50e  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001c513  xor     r9d, r9d; msWindowLength
0x18001c516  mov     cs:byte_180044BE8, 1
0x18001c51d  xor     r8d, r8d; msPeriod
0x18001c520  call    cs:__imp_SetThreadpoolTimer
0x18001c526  add     rsp, 28h
0x18001c52a  retn
```

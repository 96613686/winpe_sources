# LMCallback::AutoStop(void)

- ea: `0x180001b00`
- end: `0x180001b1e`
- name: `?AutoStop@LMCallback@@UEAA_NXZ`
- size: `30`
- prototype: `bool __fastcall(LMCallback *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180001b00`
- `0x1800042ac`

## import_xrefs

- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x180001b0d`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x180001b0d`

## pseudocode

```c
bool __fastcall LMCallback::AutoStop(LMCallback *this)
{
  int v1; // eax

  if ( !(unsigned __int8)IsShouldLicenseManagerServiceAutoStopPresent(this)
    || (v1 = ShouldLicenseManagerServiceAutoStop()) != 0 )
  {
    LOBYTE(v1) = 1;
  }
  return v1;
}

```

## disassembly

```asm
0x180001b00  sub     rsp, 28h
0x180001b04  call    IsShouldLicenseManagerServiceAutoStopPresent
0x180001b09  test    al, al
0x180001b0b  jz      short loc_180001B17
0x180001b0d  call    cs:__imp_ShouldLicenseManagerServiceAutoStop
0x180001b13  test    eax, eax
0x180001b15  jz      short loc_180001B19
0x180001b17  mov     al, 1
0x180001b19  add     rsp, 28h
0x180001b1d  retn
```

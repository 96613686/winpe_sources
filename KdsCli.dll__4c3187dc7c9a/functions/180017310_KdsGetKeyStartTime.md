# KdsGetKeyStartTime

- ea: `0x180017310`
- end: `0x180017389`
- name: `KdsGetKeyStartTime`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180010270`
- `0x180010cf8`
- `0x180017310`
- `0x18001a450`

## string_xrefs

- `0x18001736e`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\gmsahelp.cxx`

## pseudocode

```c
__int64 __fastcall KdsGetKeyStartTime(unsigned __int8 *a1, unsigned int a2, unsigned __int64 *a3)
{
  struct _SID_KEY_ID_HEADER *v4; // rax
  char v5; // r9
  unsigned int v6; // ebx
  char v7; // cl
  int IntervalStartTime; // eax

  v4 = ValidateSIDKeyID(a1, a2);
  if ( !v4 )
  {
    v5 = 40;
LABEL_3:
    v6 = -2146893821;
    v7 = 3;
LABEL_8:
    SidKeyDebugTraceError(v7, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\gmsahelp.cxx", v5);
    return v6;
  }
  if ( (*((_BYTE *)v4 + 8) & 1) != 0 )
  {
    v5 = 48;
    goto LABEL_3;
  }
  IntervalStartTime = GetIntervalStartTime(
                        0x53D1AC1000uLL,
                        *((_DWORD *)v4 + 3),
                        *((_DWORD *)v4 + 4),
                        *((_DWORD *)v4 + 5),
                        a3);
  v6 = IntervalStartTime;
  if ( IntervalStartTime < 0 )
  {
    v5 = 60;
    v7 = IntervalStartTime;
    goto LABEL_8;
  }
  return v6;
}

```

## disassembly

```asm
0x180017310  push    rbx
0x180017312  sub     rsp, 30h
0x180017316  mov     rbx, r8
0x180017319  call    ?ValidateSIDKeyID@@YAPEAU_SID_KEY_ID_HEADER@@QEAEK@Z; ValidateSIDKeyID(uchar * const,ulong)
0x18001731e  test    rax, rax
0x180017321  jnz     short loc_180017333
0x180017323  lea     r9d, [rax+28h]
0x180017327  mov     ebx, 80090003h
0x18001732c  mov     ecx, 80090003h
0x180017331  jmp     short loc_18001736E
0x180017333  test    byte ptr [rax+8], 1
0x180017337  jz      short loc_180017341
0x180017339  mov     r9d, 30h ; '0'
0x18001733f  jmp     short loc_180017327
0x180017341  mov     r9d, [rax+14h]; unsigned int
0x180017345  mov     rcx, 53D1AC1000h; unsigned __int64
0x18001734f  mov     r8d, [rax+10h]; unsigned int
0x180017353  mov     edx, [rax+0Ch]; unsigned int
0x180017356  mov     [rsp+38h+var_18], rbx; unsigned __int64 *
0x18001735b  call    ?GetIntervalStartTime@@YAJ_KKKKPEA_K@Z; GetIntervalStartTime(unsigned __int64,ulong,ulong,ulong,unsigned __int64 *)
0x180017360  mov     ebx, eax
0x180017362  test    eax, eax
0x180017364  jns     short loc_180017381
0x180017366  mov     r9d, 3Ch ; '<'; unsigned int
0x18001736c  mov     ecx, eax; unsigned int
0x18001736e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017375  lea     rdx, aHr; "hr"
0x18001737c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180017381  mov     eax, ebx
0x180017383  add     rsp, 30h
0x180017387  pop     rbx
0x180017388  retn
```

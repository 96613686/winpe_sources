# CTieringEngineLib::RegistryChangeListener(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1400086b0`
- end: `0x1400086f8`
- name: `?RegistryChangeListener@CTieringEngineLib@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `72`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140004a68`
- `0x14000860c`
- `0x1400086b0`

## pseudocode

```c
void __fastcall CTieringEngineLib::RegistryChangeListener(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  unsigned int v3; // eax

  v3 = CTieringEngineLib::RegisterForChangeNotification(Context);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v3);
  }
}

```

## disassembly

```asm
0x1400086b0  sub     rsp, 28h
0x1400086b4  mov     rcx, rdx; void *
0x1400086b7  call    ?RegisterForChangeNotification@CTieringEngineLib@@CAJPEAX@Z; CTieringEngineLib::RegisterForChangeNotification(void *)
0x1400086bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086c3  lea     rdx, WPP_GLOBAL_Control
0x1400086ca  cmp     rcx, rdx
0x1400086cd  jz      short loc_1400086F3
0x1400086cf  test    byte ptr [rcx+1Ch], 1
0x1400086d3  jz      short loc_1400086F3
0x1400086d5  cmp     byte ptr [rcx+19h], 2
0x1400086d9  jb      short loc_1400086F3
0x1400086db  mov     rcx, [rcx+10h]
0x1400086df  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x1400086e6  mov     edx, 69h ; 'i'
0x1400086eb  mov     r9d, eax
0x1400086ee  call    WPP_SF_d
0x1400086f3  add     rsp, 28h
0x1400086f7  retn
```

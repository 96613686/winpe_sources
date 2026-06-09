# ProcessDetach(HINSTANCE__ *,ulong,void *)

- ea: `0x1800028e8`
- end: `0x18000296c`
- name: `?ProcessDetach@@YAXPEAUHINSTANCE__@@KPEAX@Z`
- size: `132`
- prototype: `void __fastcall(HINSTANCE, __int64, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002974`

## callees

- `0x1800028e8`
- `0x1800029ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002927`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002927`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180002944`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180002944`

## pseudocode

```c
void __fastcall ProcessDetach(HINSTANCE a1, __int64 a2, void *a3)
{
  _QWORD *v3; // rbx
  TRACEHANDLE v4; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_98832096b68230bb9df8150bc18aef7b_Traceguids);
  DeleteCriticalSection(&g_csDqbIdleStop);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    while ( v3 )
    {
      v4 = v3[1];
      if ( v4 )
      {
        UnregisterTraceGuids(v4);
        v3[1] = 0;
      }
      v3 = (_QWORD *)*v3;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x1800028e8  mov     [rsp+arg_0], rbx
0x1800028ed  push    rdi
0x1800028ee  sub     rsp, 20h
0x1800028f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028f9  lea     rdi, WPP_GLOBAL_Control
0x180002900  cmp     rcx, rdi
0x180002903  jz      short loc_180002920
0x180002905  cmp     byte ptr [rcx+19h], 4
0x180002909  jb      short loc_180002920
0x18000290b  mov     rcx, [rcx+10h]
0x18000290f  lea     r8, WPP_98832096b68230bb9df8150bc18aef7b_Traceguids
0x180002916  mov     edx, 0Bh
0x18000291b  call    WPP_SF_
0x180002920  lea     rcx, ?g_csDqbIdleStop@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002927  call    cs:__imp_DeleteCriticalSection
0x18000292d  mov     rbx, cs:WPP_GLOBAL_Control
0x180002934  cmp     rbx, rdi
0x180002937  jz      short loc_180002961
0x180002939  jmp     short loc_180002955
0x18000293b  mov     rcx, [rbx+8]; RegistrationHandle
0x18000293f  test    rcx, rcx
0x180002942  jz      short loc_180002952
0x180002944  call    cs:__imp_UnregisterTraceGuids
0x18000294a  mov     qword ptr [rbx+8], 0
0x180002952  mov     rbx, [rbx]
0x180002955  test    rbx, rbx
0x180002958  jnz     short loc_18000293B
0x18000295a  mov     cs:WPP_GLOBAL_Control, rdi
0x180002961  mov     rbx, [rsp+28h+arg_0]
0x180002966  add     rsp, 20h
0x18000296a  pop     rdi
0x18000296b  retn
```

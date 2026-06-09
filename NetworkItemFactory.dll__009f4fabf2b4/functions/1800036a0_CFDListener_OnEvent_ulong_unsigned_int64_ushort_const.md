# CFDListener::OnEvent(ulong,unsigned __int64,ushort const *)

- ea: `0x1800036a0`
- end: `0x18000377a`
- name: `?OnEvent@CFDListener@@UEAAJK_KPEBG@Z`
- size: `218`
- prototype: `int(CFDListener *__hidden this, unsigned int, unsigned __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800036a0`
- `0x18000589c`
- `0x1800076c8`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180003711`
- `KERNEL32!CompareStringW` at `0x180003711`

## pseudocode

```c
__int64 __fastcall CFDListener::OnEvent(CFDListener *this, int a2, __int64 a3, const unsigned __int16 *a4)
{
  volatile signed __int32 *v6; // rcx
  signed __int32 v8; // r10d
  __int64 v9; // rdi
  signed __int32 v10; // edx

  v6 = (volatile signed __int32 *)((char *)this + 12);
  if ( (*v6 & 0xFFFF8000) != 0 || (v8 = *v6, v8 != _InterlockedCompareExchange(v6, v8 + 1, v8)) )
    CReaderWriterLock3::_LockSpin(v6, 2);
  if ( *((_DWORD *)this + 8) )
  {
    if ( a2 == 1000 )
    {
      v9 = *((_QWORD *)this + 3);
      if ( CompareStringW(0x7Fu, 0, a4, -1, L"Provider\\Microsoft.Networking.Netbios", -1) == 2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_182dd27e7f09338048566614cf2976f3_Traceguids);
        }
        *(_DWORD *)(v9 + 60) = 1;
      }
    }
  }
  do
    v10 = *((_DWORD *)this + 3);
  while ( v10 != _InterlockedCompareExchange((volatile signed __int32 *)this + 3, v10 - 1, v10) );
  return 0;
}

```

## disassembly

```asm
0x1800036a0  mov     [rsp+arg_0], rbx
0x1800036a5  mov     [rsp+arg_8], rsi
0x1800036aa  push    rdi
0x1800036ab  sub     rsp, 30h
0x1800036af  mov     rbx, rcx
0x1800036b2  mov     rsi, r9
0x1800036b5  add     rcx, 0Ch
0x1800036b9  mov     edi, edx
0x1800036bb  mov     r10d, [rcx]
0x1800036be  test    r10d, 0FFFF8000h
0x1800036c5  jnz     short loc_1800036D8
0x1800036c7  lea     r8d, [r10+1]
0x1800036cb  mov     eax, r10d
0x1800036ce  lock cmpxchg [rcx], r8d
0x1800036d3  cmp     r10d, eax
0x1800036d6  jz      short loc_1800036E2
0x1800036d8  mov     edx, 2
0x1800036dd  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x1800036e2  cmp     dword ptr [rbx+20h], 0
0x1800036e6  jz      short loc_180003757
0x1800036e8  cmp     edi, 3E8h
0x1800036ee  jnz     short loc_180003757
0x1800036f0  mov     rdi, [rbx+18h]
0x1800036f4  lea     rax, aProviderMicros_0; "Provider\\Microsoft.Networking.Netbios"
0x1800036fb  xor     edx, edx; dwCmpFlags
0x1800036fd  or      r9d, 0FFFFFFFFh; cchCount1
0x180003701  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180003706  mov     r8, rsi; lpString1
0x180003709  mov     [rsp+38h+lpString2], rax; lpString2
0x18000370e  lea     ecx, [rdx+7Fh]; Locale
0x180003711  call    cs:__imp_CompareStringW
0x180003717  cmp     eax, 2
0x18000371a  jnz     short loc_180003757
0x18000371c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003723  lea     rax, WPP_GLOBAL_Control
0x18000372a  cmp     rcx, rax
0x18000372d  jz      short loc_180003750
0x18000372f  cmp     byte ptr [rcx+19h], 4
0x180003733  jb      short loc_180003750
0x180003735  test    byte ptr [rcx+1Ch], 2
0x180003739  jz      short loc_180003750
0x18000373b  mov     rcx, [rcx+10h]
0x18000373f  lea     r8, WPP_182dd27e7f09338048566614cf2976f3_Traceguids
0x180003746  mov     edx, 12h
0x18000374b  call    WPP_SF_
0x180003750  mov     dword ptr [rdi+3Ch], 1
0x180003757  mov     edx, [rbx+0Ch]
0x18000375a  mov     eax, edx
0x18000375c  lea     ecx, [rdx-1]
0x18000375f  lock cmpxchg [rbx+0Ch], ecx
0x180003764  cmp     edx, eax
0x180003766  jnz     short loc_180003757
0x180003768  mov     rbx, [rsp+38h+arg_0]
0x18000376d  xor     eax, eax
0x18000376f  mov     rsi, [rsp+38h+arg_8]
0x180003774  add     rsp, 30h
0x180003778  pop     rdi
0x180003779  retn
```

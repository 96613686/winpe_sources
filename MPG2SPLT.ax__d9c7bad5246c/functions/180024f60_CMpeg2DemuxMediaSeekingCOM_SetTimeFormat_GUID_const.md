# CMpeg2DemuxMediaSeekingCOM::SetTimeFormat(_GUID const *)

- ea: `0x180024f60`
- end: `0x180025065`
- name: `?SetTimeFormat@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEBU_GUID@@@Z`
- size: `261`
- prototype: `int(CMpeg2DemuxMediaSeekingCOM *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180024804`
- `0x180024f60`
- `0x180033df1`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180025025`
- `KERNEL32!LeaveCriticalSection` at `0x180025025`
- `KERNEL32!EnterCriticalSection` at `0x180024fba`
- `KERNEL32!EnterCriticalSection` at `0x180024fba`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::SetTimeFormat(CMpeg2DemuxMediaSeekingCOM *this, const struct _GUID *a2)
{
  CMpeg2DemuxMediaSeekingCore *v4; // rdi
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rcx
  __int128 v8; // xmm0
  unsigned int v9; // ebx

  if ( !a2 )
    return 2147500035LL;
  v4 = (CMpeg2DemuxMediaSeekingCore *)*((_QWORD *)this + 6);
  v5 = *((_QWORD *)v4 + 5);
  v6 = *(_QWORD *)(v5 + 336);
  if ( !v6 || !*(_DWORD *)(v6 + 176) )
    return 2147549183LL;
  if ( (unsigned int)CMpeg2DemuxMediaSeekingCore::IsSeekingPin(v4, *((struct CMPEG2DemuxOutputPin **)this + 1)) )
  {
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(v5 + 80));
    v7 = *((_QWORD *)v4 + 5);
    if ( *(_DWORD *)(v7 + 40) )
    {
      v9 = -2147220953;
    }
    else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&TIME_FORMAT_BYTE.Data1
           && *(_QWORD *)a2->Data4 == *(_QWORD *)TIME_FORMAT_BYTE.Data4
           && *((_QWORD *)v4 + 2) != -1
           || *(_QWORD *)&a2->Data1 == *(_QWORD *)&TIME_FORMAT_MEDIA_TIME.Data1
           && *(_QWORD *)a2->Data4 == *(_QWORD *)TIME_FORMAT_MEDIA_TIME.Data4
           && *((_QWORD *)v4 + 3) != -1 )
    {
      v8 = (__int128)*a2;
      v9 = 0;
      *(_OWORD *)v4 = v8;
    }
    else
    {
      v9 = -2147024809;
    }
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v7 + 80));
  }
  else
  {
    return memcmp_0(a2, &TIME_FORMAT_NONE, 0x10u) != 0 ? 0x80004005 : 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180024f60  mov     [rsp+arg_0], rbx
0x180024f65  mov     [rsp+arg_8], rsi
0x180024f6a  push    rdi
0x180024f6b  sub     rsp, 20h
0x180024f6f  mov     rbx, rdx
0x180024f72  test    rdx, rdx
0x180024f75  jnz     short loc_180024F81
0x180024f77  mov     eax, 80004003h
0x180024f7c  jmp     loc_180025055
0x180024f81  mov     rdi, [rcx+30h]
0x180024f85  mov     rsi, [rdi+28h]
0x180024f89  mov     rax, [rsi+150h]
0x180024f90  test    rax, rax
0x180024f93  jz      loc_180025050
0x180024f99  cmp     dword ptr [rax+0B0h], 0
0x180024fa0  jz      loc_180025050
0x180024fa6  mov     rdx, [rcx+8]; struct CMPEG2DemuxOutputPin *
0x180024faa  mov     rcx, rdi; this
0x180024fad  call    ?IsSeekingPin@CMpeg2DemuxMediaSeekingCore@@QEAAHPEAVCMPEG2DemuxOutputPin@@@Z; CMpeg2DemuxMediaSeekingCore::IsSeekingPin(CMPEG2DemuxOutputPin *)
0x180024fb2  test    eax, eax
0x180024fb4  jz      short loc_18002502D
0x180024fb6  mov     rcx, [rsi+50h]; lpCriticalSection
0x180024fba  call    cs:__imp_EnterCriticalSection
0x180024fc0  mov     rcx, [rdi+28h]
0x180024fc4  cmp     dword ptr [rcx+28h], 0
0x180024fc8  jnz     short loc_18002501C
0x180024fca  mov     rax, [rbx]
0x180024fcd  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data1
0x180024fd4  jnz     short loc_180024FEA
0x180024fd6  mov     rax, [rbx+8]
0x180024fda  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data4
0x180024fe1  jnz     short loc_180024FEA
0x180024fe3  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x180024fe8  jnz     short loc_18002500A
0x180024fea  mov     rax, [rbx]
0x180024fed  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x180024ff4  jnz     short loc_180025015
0x180024ff6  mov     rax, [rbx+8]
0x180024ffa  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data4
0x180025001  jnz     short loc_180025015
0x180025003  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x180025008  jz      short loc_180025015
0x18002500a  movups  xmm0, xmmword ptr [rbx]
0x18002500d  xor     ebx, ebx
0x18002500f  movdqu  xmmword ptr [rdi], xmm0
0x180025013  jmp     short loc_180025021
0x180025015  mov     ebx, 80070057h
0x18002501a  jmp     short loc_180025021
0x18002501c  mov     ebx, 80040227h
0x180025021  mov     rcx, [rcx+50h]; lpCriticalSection
0x180025025  call    cs:__imp_LeaveCriticalSection
0x18002502b  jmp     short loc_18002504C
0x18002502d  mov     r8d, 10h; Size
0x180025033  lea     rdx, TIME_FORMAT_NONE; Buf2
0x18002503a  mov     rcx, rbx; Buf1
0x18002503d  call    memcmp_0
0x180025042  neg     eax
0x180025044  sbb     ebx, ebx
0x180025046  and     ebx, 80004005h
0x18002504c  mov     eax, ebx
0x18002504e  jmp     short loc_180025055
0x180025050  mov     eax, 8000FFFFh
0x180025055  mov     rbx, [rsp+28h+arg_0]
0x18002505a  mov     rsi, [rsp+28h+arg_8]
0x18002505f  add     rsp, 20h
0x180025063  pop     rdi
0x180025064  retn
```

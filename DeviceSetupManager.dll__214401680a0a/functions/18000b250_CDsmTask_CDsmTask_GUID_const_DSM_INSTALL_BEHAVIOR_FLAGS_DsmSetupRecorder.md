# CDsmTask::CDsmTask(_GUID const &,DSM_INSTALL_BEHAVIOR_FLAGS,DsmSetupRecorder &)

- ea: `0x18000b250`
- end: `0x18000b47f`
- name: `??0CDsmTask@@QEAA@AEBU_GUID@@W4DSM_INSTALL_BEHAVIOR_FLAGS@@AEAVDsmSetupRecorder@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, const GUID *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015e74`

## callees

- `0x18000b250`
- `0x18000b740`
- `0x18001ba48`
- `0x180031408`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000b301`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000b40b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000b301`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000b40b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b3dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b3f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b3dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b3f7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b32b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b3cd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b32b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b3cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDsmTask::CDsmTask(__int64 a1, const GUID *a2, int a3, __int64 a4)
{
  __int64 v4; // r15
  unsigned int ContainerUINT; // eax
  int v10; // r8d

  v4 = a1 + 8;
  *(_QWORD *)a1 = &CDsmTask::`vftable';
  *(GUID *)(a1 + 8) = *a2;
  *(_QWORD *)(a1 + 104) = &CDsmPropertyCache::`vftable';
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_DWORD *)(a1 + 160) = 10;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_DWORD *)(a1 + 208) = 10;
  *(GUID *)(a1 + 216) = *a2;
  *(_QWORD *)(a1 + 312) = 0;
  *(_DWORD *)(a1 + 320) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 112));
  memset_0((void *)(a1 + 232), 0, 0x4Eu);
  StringFromGUID2(a2, (LPOLESTR)(a1 + 232), 39);
  *(_BYTE *)(a1 + 332) = 0;
  *(_DWORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 336) = 1;
  *(_DWORD *)(a1 + 344) = a3;
  *(_DWORD *)(a1 + 348) = 0;
  *(_QWORD *)(a1 + 352) = a4;
  *(_QWORD *)(a1 + 368) = 0;
  *(_QWORD *)(a1 + 376) = 0;
  *(_QWORD *)(a1 + 384) = 0;
  *(_QWORD *)(a1 + 392) = 0;
  *(_QWORD *)(a1 + 400) = 0;
  *(_BYTE *)(a1 + 408) = 0;
  *(_DWORD *)(a1 + 412) = 0;
  *(_DWORD *)(a1 + 416) = -1;
  *(_QWORD *)(a1 + 420) = 0;
  *(_WORD *)(a1 + 428) = 0;
  *(_DWORD *)(a1 + 432) = 0;
  memset_0((void *)(a1 + 24), 0, 0x4Eu);
  StringFromGUID2(a2, (LPOLESTR)(a1 + 24), 39);
  *(_QWORD *)(a1 + 384) = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 392) = CreateEventW(0, 1, 1, 0);
  InitializeSRWLock((PSRWLOCK)(a1 + 360));
  ContainerUINT = GetContainerUINT((const unsigned __int16 *)(a1 + 24), &DEVPKEY_DeviceContainer_ConfigFlags);
  if ( ContainerUINT == -1 )
    *(_BYTE *)(a1 + 332) = 1;
  *(_DWORD *)(a1 + 328) = (unsigned __int16)ContainerUINT;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v10, (unsigned __int16)ContainerUINT, v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18000b250  push    rbx
0x18000b252  push    rbp
0x18000b253  push    rsi
0x18000b254  push    rdi
0x18000b255  push    r12
0x18000b257  push    r14
0x18000b259  push    r15
0x18000b25b  sub     rsp, 30h
0x18000b25f  xor     r12d, r12d
0x18000b262  lea     r15, [rcx+8]
0x18000b266  lea     rax, ??_7CDsmTask@@6B@; const CDsmTask::`vftable'
0x18000b26d  mov     rbx, rcx
0x18000b270  mov     [rcx], rax
0x18000b273  mov     rbp, r9
0x18000b276  movups  xmm0, xmmword ptr [rdx]
0x18000b279  lea     rax, ??_7CDsmPropertyCache@@6B@; const CDsmPropertyCache::`vftable'
0x18000b280  mov     esi, r8d
0x18000b283  mov     r14, rdx
0x18000b286  movups  xmmword ptr [r15], xmm0
0x18000b28a  mov     [rcx+68h], rax
0x18000b28e  mov     [rcx+78h], r12
0x18000b292  mov     [rcx+80h], r12
0x18000b299  mov     [rcx+88h], r12
0x18000b2a0  mov     [rcx+90h], r12
0x18000b2a7  mov     [rcx+98h], r12
0x18000b2ae  mov     dword ptr [rcx+0A0h], 0Ah
0x18000b2b8  mov     [rcx+0A8h], r12
0x18000b2bf  mov     [rcx+0B0h], r12
0x18000b2c6  mov     [rcx+0B8h], r12
0x18000b2cd  mov     [rcx+0C0h], r12
0x18000b2d4  mov     [rcx+0C8h], r12
0x18000b2db  mov     dword ptr [rcx+0D0h], 0Ah
0x18000b2e5  movups  xmm0, xmmword ptr [rdx]
0x18000b2e8  movups  xmmword ptr [rcx+0D8h], xmm0
0x18000b2ef  mov     [rcx+138h], r12
0x18000b2f6  mov     [rcx+140h], r12d
0x18000b2fd  add     rcx, 70h ; 'p'; SRWLock
0x18000b301  call    cs:__imp_InitializeSRWLock
0x18000b307  xor     edx, edx; Val
0x18000b309  lea     rcx, [rbx+0E8h]; void *
0x18000b310  mov     r8d, 4Eh ; 'N'; Size
0x18000b316  call    memset_0
0x18000b31b  mov     r8d, 27h ; '''; cchMax
0x18000b321  lea     rdx, [rbx+0E8h]; lpsz
0x18000b328  mov     rcx, r14; rguid
0x18000b32b  call    cs:__imp_StringFromGUID2
0x18000b331  mov     [rbx+14Ch], r12b
0x18000b338  lea     rcx, [rbx+18h]; void *
0x18000b33c  mov     [rbx+148h], r12d
0x18000b343  xor     edx, edx; Val
0x18000b345  mov     r8d, 4Eh ; 'N'; Size
0x18000b34b  mov     qword ptr [rbx+150h], 1
0x18000b356  mov     [rbx+158h], esi
0x18000b35c  mov     [rbx+15Ch], r12d
0x18000b363  mov     [rbx+160h], rbp
0x18000b36a  mov     [rbx+170h], r12
0x18000b371  mov     [rbx+178h], r12
0x18000b378  mov     [rbx+180h], r12
0x18000b37f  mov     [rbx+188h], r12
0x18000b386  mov     [rbx+190h], r12
0x18000b38d  mov     [rbx+198h], r12b
0x18000b394  mov     [rbx+19Ch], r12d
0x18000b39b  mov     dword ptr [rbx+1A0h], 0FFFFFFFFh
0x18000b3a5  mov     [rbx+1A4h], r12
0x18000b3ac  mov     [rbx+1ACh], r12w
0x18000b3b4  mov     [rbx+1B0h], r12d
0x18000b3bb  call    memset_0
0x18000b3c0  mov     r8d, 27h ; '''; cchMax
0x18000b3c6  lea     rdx, [rbx+18h]; lpsz
0x18000b3ca  mov     rcx, r14; rguid
0x18000b3cd  call    cs:__imp_StringFromGUID2
0x18000b3d3  xor     r9d, r9d; lpName
0x18000b3d6  xor     r8d, r8d; bInitialState
0x18000b3d9  xor     edx, edx; bManualReset
0x18000b3db  xor     ecx, ecx; lpEventAttributes
0x18000b3dd  call    cs:__imp_CreateEventW
0x18000b3e3  mov     edx, 1; bManualReset
0x18000b3e8  xor     r9d, r9d; lpName
0x18000b3eb  mov     r8d, edx; bInitialState
0x18000b3ee  mov     [rbx+180h], rax
0x18000b3f5  xor     ecx, ecx; lpEventAttributes
0x18000b3f7  call    cs:__imp_CreateEventW
0x18000b3fd  lea     rcx, [rbx+168h]; SRWLock
0x18000b404  mov     [rbx+188h], rax
0x18000b40b  call    cs:__imp_InitializeSRWLock
0x18000b411  lea     rdx, DEVPKEY_DeviceContainer_ConfigFlags; struct _DEVPROPKEY *
0x18000b418  lea     rcx, [rbx+18h]; unsigned __int16 *
0x18000b41c  call    ?GetContainerUINT@@YAIPEBGAEBU_DEVPROPKEY@@@Z; GetContainerUINT(ushort const *,_DEVPROPKEY const &)
0x18000b421  cmp     eax, 0FFFFFFFFh
0x18000b424  jnz     short loc_18000B42D
0x18000b426  mov     byte ptr [rbx+14Ch], 1
0x18000b42d  movzx   r9d, ax
0x18000b431  mov     [rbx+148h], r9d
0x18000b438  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b43f  lea     rax, WPP_GLOBAL_Control
0x18000b446  cmp     rcx, rax
0x18000b449  jz      short loc_18000B46D
0x18000b44b  test    dword ptr [rcx+1Ch], 100h
0x18000b452  jz      short loc_18000B46D
0x18000b454  cmp     byte ptr [rcx+19h], 4
0x18000b458  jb      short loc_18000B46D
0x18000b45a  mov     rcx, [rcx+10h]
0x18000b45e  mov     edx, 0Ch
0x18000b463  mov     [rsp+68h+var_48], r15
0x18000b468  call    WPP_SF_D_guid_
0x18000b46d  mov     rax, rbx
0x18000b470  add     rsp, 30h
0x18000b474  pop     r15
0x18000b476  pop     r14
0x18000b478  pop     r12
0x18000b47a  pop     rdi
0x18000b47b  pop     rsi
0x18000b47c  pop     rbp
0x18000b47d  pop     rbx
0x18000b47e  retn
```

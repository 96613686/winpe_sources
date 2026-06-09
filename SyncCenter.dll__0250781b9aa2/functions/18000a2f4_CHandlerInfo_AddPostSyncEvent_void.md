# CHandlerInfo::_AddPostSyncEvent(void)

- ea: `0x18000a2f4`
- end: `0x18000a4f9`
- name: `?_AddPostSyncEvent@CHandlerInfo@@AEAAXXZ`
- size: `517`
- prototype: `void __fastcall(LPCRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a064`

## callees

- `0x180005660`
- `0x18000a2f4`
- `0x18000a5e4`
- `0x1800167c0`
- `0x18004eca8`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a47b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a47b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a344`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a344`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a329`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a329`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a404`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a404`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a41b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a41b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a4cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a4cf`

## pseudocode

```c
void __fastcall CHandlerInfo::_AddPostSyncEvent(LPCRITICAL_SECTION *this)
{
  struct SYNCMGR_EVENTINFO *v2; // rbx
  int v3; // edi
  __int64 v4; // rdx
  _OWORD *v5; // rax
  _OWORD *v6; // rcx
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  struct SYNCMGR_EVENTINFO *v14; // rax
  _OWORD *v15; // rcx
  __int64 v16; // rdx
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  int v24; // edi
  int v25; // edi
  UINT v26; // edx
  unsigned int v27; // edi
  _BYTE v28[280]; // [rsp+20h] [rbp-118h] BYREF
  HLOCAL hMem; // [rsp+148h] [rbp+10h] BYREF
  struct SYNCMGR_EVENTINFO *v30; // [rsp+150h] [rbp+18h] BYREF

  v30 = (struct SYNCMGR_EVENTINFO *)operator new(0xB3Cu);
  v2 = v30;
  if ( v30 )
  {
    EnterCriticalSection(this[1]);
    v3 = ((__int64 (__fastcall *)(char *))this[5]->DebugInfo)((char *)this + 40);
    LeaveCriticalSection(this[1]);
    v4 = 2;
    v5 = (_OWORD *)((char *)this + 116);
    v6 = v28;
    do
    {
      v7 = v5[1];
      *v6 = *v5;
      v8 = v5[2];
      v6[1] = v7;
      v9 = v5[3];
      v6[2] = v8;
      v10 = v5[4];
      v6[3] = v9;
      v11 = v5[5];
      v6[4] = v10;
      v12 = v5[6];
      v6[5] = v11;
      v13 = v5[7];
      v5 += 8;
      v6[6] = v12;
      v6[7] = v13;
      v6 += 8;
      --v4;
    }
    while ( v4 );
    v14 = v2;
    v15 = v28;
    v16 = 2;
    do
    {
      v17 = v15[1];
      *(_OWORD *)v14 = *v15;
      v18 = v15[2];
      *((_OWORD *)v14 + 1) = v17;
      v19 = v15[3];
      *((_OWORD *)v14 + 2) = v18;
      v20 = v15[4];
      *((_OWORD *)v14 + 3) = v19;
      v21 = v15[5];
      *((_OWORD *)v14 + 4) = v20;
      v22 = v15[6];
      *((_OWORD *)v14 + 5) = v21;
      v23 = v15[7];
      v15 += 8;
      *((_OWORD *)v14 + 6) = v22;
      *((_OWORD *)v14 + 7) = v23;
      v14 = (struct SYNCMGR_EVENTINFO *)((char *)v14 + 128);
      --v16;
    }
    while ( v16 );
    CoCreateGuid((GUID *)v2 + 16);
    *((_DWORD *)v2 + 68) = 1;
    GetSystemTimeAsFileTime((LPFILETIME)((char *)v2 + 2868));
    v24 = v3 - 4;
    if ( v24 && (v25 = v24 - 2) != 0 )
    {
      if ( v25 == 1 )
      {
        v26 = 3130;
        *((_DWORD *)v2 + 69) = 0x20000000;
        v27 = 3135;
      }
      else
      {
        v26 = 3120;
        *((_DWORD *)v2 + 69) = 0x10000000;
        v27 = 3125;
      }
    }
    else
    {
      v26 = 3110;
      *((_DWORD *)v2 + 69) = 0x80000000;
      v27 = 3115;
    }
    LoadStringW(g_hmodThisDll, v26, (LPWSTR)v2 + 142, 128);
    hMem = 0;
    if ( (int)SHFormatResMessageArgAlloc(g_hmodThisDll, v27, &hMem, (char *)this + 372) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)v2 + 270, 0x104u, (const unsigned __int16 *)hMem);
      LocalFree(hMem);
    }
    CHandlerInfo::AddEvent((CHandlerInfo *)this, &v30);
  }
}

```

## disassembly

```asm
0x18000a2f4  mov     [rsp+arg_0], rbx
0x18000a2f9  push    rsi
0x18000a2fa  push    rdi
0x18000a2fb  push    r14
0x18000a2fd  sub     rsp, 120h
0x18000a304  mov     rsi, rcx
0x18000a307  mov     ecx, 0B3Ch; unsigned __int64
0x18000a30c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a311  mov     [rsp+138h+arg_10], rax
0x18000a319  mov     rbx, rax
0x18000a31c  test    rax, rax
0x18000a31f  jz      loc_18000A4E5
0x18000a325  mov     rcx, [rsi+8]; lpCriticalSection
0x18000a329  call    cs:__imp_EnterCriticalSection
0x18000a32f  lea     rcx, [rsi+28h]
0x18000a333  mov     rdx, [rcx]
0x18000a336  mov     rax, [rdx]
0x18000a339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a33e  mov     rcx, [rsi+8]; lpCriticalSection
0x18000a342  mov     edi, eax
0x18000a344  call    cs:__imp_LeaveCriticalSection
0x18000a34a  mov     edx, 2
0x18000a34f  lea     rax, [rsi+74h]
0x18000a353  lea     rcx, [rsp+138h+var_118]
0x18000a358  lea     r14d, [rdx+7Eh]
0x18000a35c  movups  xmm0, xmmword ptr [rax]
0x18000a35f  movups  xmm1, xmmword ptr [rax+10h]
0x18000a363  movups  xmmword ptr [rcx], xmm0
0x18000a366  movups  xmm0, xmmword ptr [rax+20h]
0x18000a36a  movups  xmmword ptr [rcx+10h], xmm1
0x18000a36e  movups  xmm1, xmmword ptr [rax+30h]
0x18000a372  movups  xmmword ptr [rcx+20h], xmm0
0x18000a376  movups  xmm0, xmmword ptr [rax+40h]
0x18000a37a  movups  xmmword ptr [rcx+30h], xmm1
0x18000a37e  movups  xmm1, xmmword ptr [rax+50h]
0x18000a382  movups  xmmword ptr [rcx+40h], xmm0
0x18000a386  movups  xmm0, xmmword ptr [rax+60h]
0x18000a38a  movups  xmmword ptr [rcx+50h], xmm1
0x18000a38e  movups  xmm1, xmmword ptr [rax+70h]
0x18000a392  add     rax, r14
0x18000a395  movups  xmmword ptr [rcx+60h], xmm0
0x18000a399  movups  xmmword ptr [rcx+70h], xmm1
0x18000a39d  add     rcx, r14
0x18000a3a0  sub     rdx, 1
0x18000a3a4  jnz     short loc_18000A35C
0x18000a3a6  mov     rax, rbx
0x18000a3a9  lea     rcx, [rsp+138h+var_118]
0x18000a3ae  mov     edx, 2
0x18000a3b3  movups  xmm0, xmmword ptr [rcx]
0x18000a3b6  movups  xmm1, xmmword ptr [rcx+10h]
0x18000a3ba  movups  xmmword ptr [rax], xmm0
0x18000a3bd  movups  xmm0, xmmword ptr [rcx+20h]
0x18000a3c1  movups  xmmword ptr [rax+10h], xmm1
0x18000a3c5  movups  xmm1, xmmword ptr [rcx+30h]
0x18000a3c9  movups  xmmword ptr [rax+20h], xmm0
0x18000a3cd  movups  xmm0, xmmword ptr [rcx+40h]
0x18000a3d1  movups  xmmword ptr [rax+30h], xmm1
0x18000a3d5  movups  xmm1, xmmword ptr [rcx+50h]
0x18000a3d9  movups  xmmword ptr [rax+40h], xmm0
0x18000a3dd  movups  xmm0, xmmword ptr [rcx+60h]
0x18000a3e1  movups  xmmword ptr [rax+50h], xmm1
0x18000a3e5  movups  xmm1, xmmword ptr [rcx+70h]
0x18000a3e9  add     rcx, r14
0x18000a3ec  movups  xmmword ptr [rax+60h], xmm0
0x18000a3f0  movups  xmmword ptr [rax+70h], xmm1
0x18000a3f4  add     rax, r14
0x18000a3f7  sub     rdx, 1
0x18000a3fb  jnz     short loc_18000A3B3
0x18000a3fd  lea     rcx, [rbx+100h]; pguid
0x18000a404  call    cs:__imp_CoCreateGuid
0x18000a40a  lea     rcx, [rbx+0B34h]; lpSystemTimeAsFileTime
0x18000a411  mov     dword ptr [rbx+110h], 1
0x18000a41b  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a421  sub     edi, 4
0x18000a424  jz      short loc_18000A458
0x18000a426  sub     edi, 2
0x18000a429  jz      short loc_18000A458
0x18000a42b  cmp     edi, 1
0x18000a42e  jz      short loc_18000A444
0x18000a430  mov     edx, 0C30h
0x18000a435  mov     dword ptr [rbx+114h], 10000000h
0x18000a43f  lea     edi, [rdx+5]
0x18000a442  jmp     short loc_18000A46A
0x18000a444  mov     edx, 0C3Ah
0x18000a449  mov     dword ptr [rbx+114h], 20000000h
0x18000a453  lea     edi, [rdx+5]
0x18000a456  jmp     short loc_18000A46A
0x18000a458  mov     edx, 0C26h; uID
0x18000a45d  mov     dword ptr [rbx+114h], 80000000h
0x18000a467  lea     edi, [rdx+5]
0x18000a46a  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000a471  lea     r8, [rbx+11Ch]; lpBuffer
0x18000a478  mov     r9d, r14d; cchBufferMax
0x18000a47b  call    cs:__imp_LoadStringW
0x18000a481  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hmodThisDll
0x18000a488  lea     r9, [rsi+174h]
0x18000a48f  lea     r8, [rsp+138h+hMem]
0x18000a497  mov     [rsp+138h+hMem], 0
0x18000a4a3  mov     edx, edi
0x18000a4a5  call    SHFormatResMessageArgAlloc
0x18000a4aa  test    eax, eax
0x18000a4ac  js      short loc_18000A4D5
0x18000a4ae  mov     r8, [rsp+138h+hMem]; unsigned __int16 *
0x18000a4b6  lea     rcx, [rbx+21Ch]; unsigned __int16 *
0x18000a4bd  mov     edx, 104h; unsigned __int64
0x18000a4c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a4c7  mov     rcx, [rsp+138h+hMem]; hMem
0x18000a4cf  call    cs:__imp_LocalFree
0x18000a4d5  lea     rdx, [rsp+138h+arg_10]; struct SYNCMGR_EVENTINFO **
0x18000a4dd  mov     rcx, rsi; this
0x18000a4e0  call    ?AddEvent@CHandlerInfo@@QEAAJPEAPEAUSYNCMGR_EVENTINFO@@@Z; CHandlerInfo::AddEvent(SYNCMGR_EVENTINFO * *)
0x18000a4e5  mov     rbx, [rsp+138h+arg_0]
0x18000a4ed  add     rsp, 120h
0x18000a4f4  pop     r14
0x18000a4f6  pop     rdi
0x18000a4f7  pop     rsi
0x18000a4f8  retn
```

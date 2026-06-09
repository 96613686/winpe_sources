# CHandlerInfo::_AddPreSyncEvent(void)

- ea: `0x1800180cc`
- end: `0x180018277`
- name: `?_AddPreSyncEvent@CHandlerInfo@@AEAAXXZ`
- size: `427`
- prototype: `void __fastcall(CHandlerInfo *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001772c`
- `0x180017e70`

## callees

- `0x180005660`
- `0x18000a5e4`
- `0x1800167c0`
- `0x1800180cc`
- `0x18004eca8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800181f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800181f5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800181b8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800181b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800181cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800181cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001824c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001824c`

## pseudocode

```c
void __fastcall CHandlerInfo::_AddPreSyncEvent(CHandlerInfo *this)
{
  struct SYNCMGR_EVENTINFO *v2; // rbx
  __int64 v3; // r8
  _OWORD *v4; // rax
  _OWORD *v5; // rdx
  __int64 v6; // rcx
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  struct SYNCMGR_EVENTINFO *v14; // rax
  _OWORD *v15; // rcx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  HINSTANCE v23; // rcx
  _BYTE v24[256]; // [rsp+20h] [rbp-108h] BYREF
  HLOCAL hMem; // [rsp+138h] [rbp+10h] BYREF
  struct SYNCMGR_EVENTINFO *v26; // [rsp+140h] [rbp+18h] BYREF

  v26 = (struct SYNCMGR_EVENTINFO *)operator new(0xB3Cu);
  v2 = v26;
  if ( v26 )
  {
    v3 = 2;
    v4 = (_OWORD *)((char *)this + 116);
    v5 = v24;
    v6 = 2;
    do
    {
      v7 = v4[1];
      *v5 = *v4;
      v8 = v4[2];
      v5[1] = v7;
      v9 = v4[3];
      v5[2] = v8;
      v10 = v4[4];
      v5[3] = v9;
      v11 = v4[5];
      v5[4] = v10;
      v12 = v4[6];
      v5[5] = v11;
      v13 = v4[7];
      v4 += 8;
      v5[6] = v12;
      v5[7] = v13;
      v5 += 8;
      --v6;
    }
    while ( v6 );
    v14 = v2;
    v15 = v24;
    do
    {
      v16 = v15[1];
      *(_OWORD *)v14 = *v15;
      v17 = v15[2];
      *((_OWORD *)v14 + 1) = v16;
      v18 = v15[3];
      *((_OWORD *)v14 + 2) = v17;
      v19 = v15[4];
      *((_OWORD *)v14 + 3) = v18;
      v20 = v15[5];
      *((_OWORD *)v14 + 4) = v19;
      v21 = v15[6];
      *((_OWORD *)v14 + 5) = v20;
      v22 = v15[7];
      v15 += 8;
      *((_OWORD *)v14 + 6) = v21;
      *((_OWORD *)v14 + 7) = v22;
      v14 = (struct SYNCMGR_EVENTINFO *)((char *)v14 + 128);
      --v3;
    }
    while ( v3 );
    CoCreateGuid((GUID *)v2 + 16);
    *((_DWORD *)v2 + 68) = 1;
    GetSystemTimeAsFileTime((LPFILETIME)((char *)v2 + 2868));
    v23 = g_hmodThisDll;
    *((_DWORD *)v2 + 69) = 0x40000000;
    LoadStringW(v23, 0xC44u, (LPWSTR)v2 + 142, 128);
    hMem = 0;
    if ( (int)SHFormatResMessageArgAlloc(g_hmodThisDll, 3145, &hMem, (char *)this + 372) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)v2 + 270, 0x104u, (const unsigned __int16 *)hMem);
      LocalFree(hMem);
    }
    CHandlerInfo::AddEvent(this, &v26);
  }
}

```

## disassembly

```asm
0x1800180cc  mov     [rsp+arg_0], rbx
0x1800180d1  mov     [rsp+arg_18], rsi
0x1800180d6  push    rdi
0x1800180d7  sub     rsp, 120h
0x1800180de  mov     rdi, rcx
0x1800180e1  mov     ecx, 0B3Ch; unsigned __int64
0x1800180e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800180eb  mov     [rsp+128h+arg_10], rax
0x1800180f3  mov     rbx, rax
0x1800180f6  test    rax, rax
0x1800180f9  jz      loc_180018262
0x1800180ff  mov     r8d, 2
0x180018105  lea     rax, [rdi+74h]
0x180018109  lea     rdx, [rsp+128h+var_108]
0x18001810e  mov     ecx, r8d
0x180018111  lea     esi, [r8+7Eh]
0x180018115  movups  xmm0, xmmword ptr [rax]
0x180018118  movups  xmm1, xmmword ptr [rax+10h]
0x18001811c  movups  xmmword ptr [rdx], xmm0
0x18001811f  movups  xmm0, xmmword ptr [rax+20h]
0x180018123  movups  xmmword ptr [rdx+10h], xmm1
0x180018127  movups  xmm1, xmmword ptr [rax+30h]
0x18001812b  movups  xmmword ptr [rdx+20h], xmm0
0x18001812f  movups  xmm0, xmmword ptr [rax+40h]
0x180018133  movups  xmmword ptr [rdx+30h], xmm1
0x180018137  movups  xmm1, xmmword ptr [rax+50h]
0x18001813b  movups  xmmword ptr [rdx+40h], xmm0
0x18001813f  movups  xmm0, xmmword ptr [rax+60h]
0x180018143  movups  xmmword ptr [rdx+50h], xmm1
0x180018147  movups  xmm1, xmmword ptr [rax+70h]
0x18001814b  add     rax, rsi
0x18001814e  movups  xmmword ptr [rdx+60h], xmm0
0x180018152  movups  xmmword ptr [rdx+70h], xmm1
0x180018156  add     rdx, rsi
0x180018159  sub     rcx, 1
0x18001815d  jnz     short loc_180018115
0x18001815f  mov     rax, rbx
0x180018162  lea     rcx, [rsp+128h+var_108]
0x180018167  movups  xmm0, xmmword ptr [rcx]
0x18001816a  movups  xmm1, xmmword ptr [rcx+10h]
0x18001816e  movups  xmmword ptr [rax], xmm0
0x180018171  movups  xmm0, xmmword ptr [rcx+20h]
0x180018175  movups  xmmword ptr [rax+10h], xmm1
0x180018179  movups  xmm1, xmmword ptr [rcx+30h]
0x18001817d  movups  xmmword ptr [rax+20h], xmm0
0x180018181  movups  xmm0, xmmword ptr [rcx+40h]
0x180018185  movups  xmmword ptr [rax+30h], xmm1
0x180018189  movups  xmm1, xmmword ptr [rcx+50h]
0x18001818d  movups  xmmword ptr [rax+40h], xmm0
0x180018191  movups  xmm0, xmmword ptr [rcx+60h]
0x180018195  movups  xmmword ptr [rax+50h], xmm1
0x180018199  movups  xmm1, xmmword ptr [rcx+70h]
0x18001819d  add     rcx, rsi
0x1800181a0  movups  xmmword ptr [rax+60h], xmm0
0x1800181a4  movups  xmmword ptr [rax+70h], xmm1
0x1800181a8  add     rax, rsi
0x1800181ab  sub     r8, 1
0x1800181af  jnz     short loc_180018167
0x1800181b1  lea     rcx, [rbx+100h]; pguid
0x1800181b8  call    cs:__imp_CoCreateGuid
0x1800181be  lea     rcx, [rbx+0B34h]; lpSystemTimeAsFileTime
0x1800181c5  mov     dword ptr [rbx+110h], 1
0x1800181cf  call    cs:__imp_GetSystemTimeAsFileTime
0x1800181d5  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800181dc  lea     r8, [rbx+11Ch]; lpBuffer
0x1800181e3  mov     r9d, esi; cchBufferMax
0x1800181e6  mov     dword ptr [rbx+114h], 40000000h
0x1800181f0  mov     edx, 0C44h; uID
0x1800181f5  call    cs:__imp_LoadStringW
0x1800181fb  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hmodThisDll
0x180018202  lea     r9, [rdi+174h]
0x180018209  lea     r8, [rsp+128h+hMem]
0x180018211  mov     [rsp+128h+hMem], 0
0x18001821d  mov     edx, 0C49h
0x180018222  call    SHFormatResMessageArgAlloc
0x180018227  test    eax, eax
0x180018229  js      short loc_180018252
0x18001822b  mov     r8, [rsp+128h+hMem]; unsigned __int16 *
0x180018233  lea     rcx, [rbx+21Ch]; unsigned __int16 *
0x18001823a  mov     edx, 104h; unsigned __int64
0x18001823f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018244  mov     rcx, [rsp+128h+hMem]; hMem
0x18001824c  call    cs:__imp_LocalFree
0x180018252  lea     rdx, [rsp+128h+arg_10]; struct SYNCMGR_EVENTINFO **
0x18001825a  mov     rcx, rdi; this
0x18001825d  call    ?AddEvent@CHandlerInfo@@QEAAJPEAPEAUSYNCMGR_EVENTINFO@@@Z; CHandlerInfo::AddEvent(SYNCMGR_EVENTINFO * *)
0x180018262  lea     r11, [rsp+128h+var_8]
0x18001826a  mov     rbx, [r11+10h]
0x18001826e  mov     rsi, [r11+28h]
0x180018272  mov     rsp, r11
0x180018275  pop     rdi
0x180018276  retn
```

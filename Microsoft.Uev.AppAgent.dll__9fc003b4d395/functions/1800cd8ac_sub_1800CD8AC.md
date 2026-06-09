# sub_1800CD8AC

- ea: `0x1800cd8ac`
- end: `0x1800ce351`
- name: `sub_1800CD8AC`
- size: `2725`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config`

## callers

- `0x1800ce358`

## callees

- `0x1800048f0`
- `0x18001916c`
- `0x18001abf0`
- `0x18001d0f4`
- `0x18001faa8`
- `0x180020dcc`
- `0x180023878`
- `0x1800245f0`
- `0x180025918`
- `0x180025a94`
- `0x180028810`
- `0x1800296f8`
- `0x18002b4a4`
- `0x180038800`
- `0x180038b44`
- `0x1800453ac`
- `0x180087970`
- `0x180088728`
- `0x18008925c`
- `0x180089f34`
- `0x18008b18c`
- `0x1800cb7f0`
- `0x1800cd8ac`
- `0x1800dd884`
- `0x180135010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800cd95a`
- `KERNEL32!GetCurrentThreadId` at `0x1800cd95a`
- `KERNEL32!SetEvent` at `0x1800ce024`
- `KERNEL32!SetEvent` at `0x1800ce024`

## string_xrefs

- `0x1800cda22`: `ImportSettingsWork::RestoreBackupSettings() - Delete package: %1%`
- `0x1800cdd77`: `ImportSettingsWork::RestoreBackupSettings() -clearing restore TimeStamp for template %1% faild with error %2%`
- `0x1800cdb7f`: `ImportSettingsWork::RestoreBackupSettings() - Could not find package path for: %1%`
- `0x1800cdef9`: `ImportSettingsWork::RestoreBackupSettings() -clearing restore Type for template %1% faild with error %2%`

## pseudocode

```c
__int64 __fastcall sub_1800CD8AC(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // rdi
  __int64 v5; // r14
  DWORD CurrentThreadId; // ebx
  volatile __int32 *v7; // r13
  int v8; // eax
  __int64 v9; // rcx
  __int64 *v10; // rax
  __int64 *v11; // rbx
  __int64 *v12; // rdi
  __int64 v13; // rcx
  __int64 *v14; // rax
  __int64 *v15; // rbx
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  __int64 *v20; // rdi
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 *v23; // rax
  __int64 *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 *v27; // rdi
  __int64 v28; // rcx
  __int64 *v29; // rax
  __int64 *v30; // rax
  __int64 *v31; // rbx
  volatile signed __int32 *v33; // rcx
  signed __int32 v34; // eax
  HANDLE v35; // rax
  __int64 v36; // rdi
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 *v39; // rdi
  __int64 v40; // rcx
  __int64 *v41; // rbx
  __int64 *v42; // rax
  __int64 *v43; // rax
  __int64 *v44; // rbx
  unsigned int v45; // r14d
  volatile signed __int32 *v46; // rbx
  volatile signed __int32 *v47; // rbx
  __int64 *v49; // [rsp+30h] [rbp-468h] BYREF
  __int64 (__fastcall *v50)(); // [rsp+38h] [rbp-460h]
  __int64 (__fastcall *v51)(); // [rsp+40h] [rbp-458h]
  __int128 v52; // [rsp+50h] [rbp-448h] BYREF
  __int128 v53; // [rsp+60h] [rbp-438h]
  __int128 v54; // [rsp+70h] [rbp-428h] BYREF
  __int128 v55; // [rsp+80h] [rbp-418h]
  __int64 v56; // [rsp+90h] [rbp-408h]
  __int64 v57; // [rsp+98h] [rbp-400h]
  __int128 v58; // [rsp+A0h] [rbp-3F8h] BYREF
  __int128 v59; // [rsp+B0h] [rbp-3E8h] BYREF
  __int64 *v60; // [rsp+C0h] [rbp-3D8h]
  __int64 v61; // [rsp+D0h] [rbp-3C8h]
  _QWORD *v62; // [rsp+D8h] [rbp-3C0h]
  __int64 v63; // [rsp+E0h] [rbp-3B8h]
  __int64 v64; // [rsp+E8h] [rbp-3B0h]
  _BYTE v65[272]; // [rsp+F0h] [rbp-3A8h] BYREF
  _BYTE v66[272]; // [rsp+200h] [rbp-298h] BYREF
  int v67; // [rsp+310h] [rbp-188h] BYREF
  __int64 v68; // [rsp+318h] [rbp-180h] BYREF
  _QWORD v69[4]; // [rsp+320h] [rbp-178h] BYREF
  _OWORD FileName[2]; // [rsp+340h] [rbp-158h] BYREF
  _QWORD v71[3]; // [rsp+360h] [rbp-138h] BYREF
  _QWORD v72[5]; // [rsp+378h] [rbp-120h] BYREF
  _QWORD v73[4]; // [rsp+3A0h] [rbp-F8h] BYREF
  _QWORD v74[4]; // [rsp+3C0h] [rbp-D8h] BYREF
  _BYTE v75[80]; // [rsp+3E0h] [rbp-B8h] BYREF
  __int64 v76; // [rsp+430h] [rbp-68h]

  v56 = a3;
  v4 = a1;
  v57 = a1;
  v61 = a1;
  v62 = a2;
  v63 = a3;
  sub_18001FAA8((__int64)v71, L"Orchestrator", L"ImportSettingsWork::RestoreBackupSettings()");
  v68 = 0;
  v67 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a2 + 16LL))(*a2, v69);
  v5 = v4 + 56;
  v64 = v4 + 56;
  *(_QWORD *)&v58 = v4 + 56;
  CurrentThreadId = GetCurrentThreadId();
  v7 = (volatile __int32 *)(v4 + 60);
  *(_QWORD *)&v59 = v4 + 60;
  if ( *(_DWORD *)(v4 + 60) == CurrentThreadId )
  {
    ++*(_DWORD *)v5;
  }
  else
  {
    sub_180087970(v4 + 64);
    _InterlockedExchange(v7, CurrentThreadId);
    *(_DWORD *)v5 = 1;
  }
  FileName[0] = 0;
  FileName[1] = _mm_load_si128((const __m128i *)&xmmword_1801685F0);
  LOWORD(FileName[0]) = 0;
  v8 = sub_180089F34(v69, FileName, 3);
  v67 = v8;
  if ( v8 < 0 )
  {
    if ( v8 == -2147024894 )
    {
      v67 = 0;
    }
    else if ( (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 8) != 0 )
    {
      v12 = (__int64 *)sub_180025A94();
      sub_180025A94();
      v52 = 0;
      v53 = 0;
      sub_18001916C(&v52, L"ImportSettingsWork::RestoreBackupSettings() - Could not find package path for: %1%", 0x52u);
      v14 = (__int64 *)sub_180038B44(v13, (__int64)v65, (__int64)&v52);
      v49 = v69;
      v50 = guard_check_icall_nop;
      v51 = (__int64 (__fastcall *)())sub_180018450;
      v15 = sub_18001ABF0(v14, (__int64)&v49);
      v54 = 0;
      v55 = 0;
      sub_18001916C(&v54, L"Orchestrator", 0xCu);
      sub_180038800(v12, 8u, (__int64)&v54, (__int64)v15);
      sub_180028810(&v54);
      sub_180020DCC((__int64)v65);
      sub_180028810(&v52);
      v4 = v57;
    }
  }
  else
  {
    if ( (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 8) != 0 )
    {
      v60 = (__int64 *)sub_180025A94();
      sub_180025A94();
      v54 = 0;
      v55 = 0;
      sub_18001916C(&v54, L"ImportSettingsWork::RestoreBackupSettings() - Delete package: %1%", 0x41u);
      v10 = (__int64 *)sub_180038B44(v9, (__int64)v65, (__int64)&v54);
      v49 = (__int64 *)FileName;
      v50 = guard_check_icall_nop;
      v51 = sub_18002D830;
      v11 = sub_18001ABF0(v10, (__int64)&v49);
      v52 = 0;
      v53 = 0;
      sub_18001916C(&v52, L"Orchestrator", 0xCu);
      sub_180038800(v60, 8u, (__int64)&v52, (__int64)v11);
      sub_180028810(&v52);
      sub_180020DCC((__int64)v65);
      sub_180028810(&v54);
    }
    sub_1800453AC((const WCHAR *)FileName, 0);
  }
  if ( v67 >= 0 )
  {
    sub_180088728(v75, v69, 1);
    (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(*(_QWORD *)*a2 + 56LL))(*a2, v75, *(_QWORD *)(v4 + 184));
    sub_1800DD884(v75);
    v67 = sub_18008B18C(v75, *(unsigned int *)(v76 + 480));
    sub_18008925C(v75);
    if ( v67 >= 0 )
    {
      v17 = sub_180025918(v16);
      v68 = 0x200000002LL;
      v18 = *(_QWORD *)(v17 + 19376);
      if ( v18
        && (*(unsigned __int8 (__fastcall **)(__int64, __int64, _QWORD *, __int64 *))((v18 & 0xFFFFFFFFFFFFFFFEuLL) + 8))(
             v17 + 19384,
             2,
             v69,
             &v68) )
      {
        LODWORD(v68) = 0;
      }
      else if ( (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 1) != 0 )
      {
        v20 = (__int64 *)sub_180025A94();
        sub_180025A94();
        v52 = 0;
        v53 = 0;
        sub_18001916C(
          &v52,
          L"ImportSettingsWork::RestoreBackupSettings() -clearing restore TimeStamp for template %1% faild with error %2%",
          0x6Du);
        v22 = (__int64 *)sub_180038B44(v21, (__int64)v65, (__int64)&v52);
        v49 = v69;
        v50 = guard_check_icall_nop;
        v51 = (__int64 (__fastcall *)())sub_180018450;
        v23 = sub_18001ABF0(v22, (__int64)&v49);
        v49 = &v68;
        v50 = guard_check_icall_nop;
        v51 = sub_18001AB60;
        v24 = sub_18001ABF0(v23, (__int64)&v49);
        v54 = 0;
        v55 = 0;
        sub_18001916C(&v54, L"Orchestrator", 0xCu);
        sub_180038800(v20, 1u, (__int64)&v54, (__int64)v24);
        sub_180028810(&v54);
        sub_180020DCC((__int64)v65);
        sub_180028810(&v52);
      }
      v25 = sub_180025918(v19);
      v68 = 0x200000002LL;
      v26 = *(_QWORD *)(v25 + 19648);
      if ( v26
        && (*(unsigned __int8 (__fastcall **)(__int64, __int64, _QWORD *, __int64 *))((v26 & 0xFFFFFFFFFFFFFFFEuLL) + 8))(
             v25 + 19656,
             2,
             v69,
             &v68) )
      {
        LODWORD(v68) = 0;
      }
      else if ( (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 1) != 0 )
      {
        v27 = (__int64 *)sub_180025A94();
        sub_180025A94();
        v52 = 0;
        v53 = 0;
        sub_18001916C(
          &v52,
          L"ImportSettingsWork::RestoreBackupSettings() -clearing restore Type for template %1% faild with error %2%",
          0x68u);
        v29 = (__int64 *)sub_180038B44(v28, (__int64)v65, (__int64)&v52);
        v49 = v69;
        v50 = guard_check_icall_nop;
        v51 = (__int64 (__fastcall *)())sub_180018450;
        v30 = sub_18001ABF0(v29, (__int64)&v49);
        v49 = &v68;
        v50 = guard_check_icall_nop;
        v51 = sub_18001AB60;
        v31 = sub_18001ABF0(v30, (__int64)&v49);
        v54 = 0;
        v55 = 0;
        sub_18001916C(&v54, L"Orchestrator", 0xCu);
        sub_180038800(v27, 1u, (__int64)&v54, (__int64)v31);
        sub_180028810(&v54);
        sub_180020DCC((__int64)v65);
        sub_180028810(&v52);
      }
    }
  }
  sub_180028810(FileName);
  if ( (*(_DWORD *)v5)-- == 1 )
  {
    _InterlockedExchange(v7, 0);
    v33 = (volatile signed __int32 *)(v5 + 8);
    v34 = _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 8), 0x80000000);
    if ( (v34 & 0x40000000) == 0 && v34 != 0x80000000 && !_interlockedbittestandset(v33, 0x1Eu) )
    {
      v35 = sub_1800296F8((__int64)v33);
      SetEvent(v35);
    }
  }
  v36 = v56;
  if ( v67 >= 0 )
  {
    v59 = 0;
    v37 = *(_QWORD *)(v56 + 8);
    if ( v37 )
      _InterlockedAdd((volatile signed __int32 *)(v37 + 8), 1u);
    v59 = *(_OWORD *)v36;
    v58 = 0;
    v38 = a2[1];
    if ( v38 )
      _InterlockedAdd((volatile signed __int32 *)(v38 + 8), 1u);
    v58 = *(_OWORD *)a2;
    v67 = sub_1800CB7F0(v57, &v58, &v59);
    if ( v67 < 0 && (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 1) != 0 )
    {
      v39 = (__int64 *)sub_180025A94();
      sub_180025A94();
      v52 = 0;
      v53 = 0;
      sub_18001916C(&v52, L"ImportSettingsWork::RestoreBackupSettings() -ImportSettings() failed with error %1%", 0x53u);
      v41 = (__int64 *)sub_180038B44(v40, (__int64)v66, (__int64)&v52);
      v42 = (__int64 *)sub_18001D0F4(v65, L"0x%02x");
      v49 = (__int64 *)&v67;
      v50 = guard_check_icall_nop;
      v51 = sub_18001AB60;
      v43 = sub_18001ABF0(v42, (__int64)&v49);
      v49 = (__int64 *)sub_18002B4A4(v43, FileName);
      v50 = guard_check_icall_nop;
      v51 = (__int64 (__fastcall *)())sub_180018450;
      v44 = sub_18001ABF0(v41, (__int64)&v49);
      v54 = 0;
      v55 = 0;
      sub_18001916C(&v54, L"Orchestrator", 0xCu);
      sub_180038800(v39, 1u, (__int64)&v54, (__int64)v44);
      sub_180028810(&v54);
      sub_180028810(FileName);
      sub_180020DCC((__int64)v65);
      sub_180020DCC((__int64)v66);
      sub_180028810(&v52);
      v36 = v56;
    }
  }
  v45 = v67;
  sub_180028810(v69);
  v71[0] = &Uev::ScopeTracker::`vftable';
  v71[2] = sub_1800245F0();
  sub_180023878((__int64)v71, (__int64)L"<--");
  sub_180028810(v74);
  sub_180028810(v73);
  sub_180028810(v72);
  v46 = (volatile signed __int32 *)a2[1];
  if ( v46 )
  {
    if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
      if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
    }
  }
  v47 = *(volatile signed __int32 **)(v36 + 8);
  if ( v47 )
  {
    if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
      if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
    }
  }
  return v45;
}

```

## disassembly

```asm
0x1800cd8ac  mov     r11, rsp
0x1800cd8af  push    rbx
0x1800cd8b0  push    rsi
0x1800cd8b1  push    rdi
0x1800cd8b2  push    r12
0x1800cd8b4  push    r13
0x1800cd8b6  push    r14
0x1800cd8b8  push    r15
0x1800cd8ba  sub     rsp, 460h
0x1800cd8c1  mov     rax, cs:__security_cookie
0x1800cd8c8  xor     rax, rsp
0x1800cd8cb  mov     [rsp+498h+var_48], rax
0x1800cd8d3  mov     rbx, r8
0x1800cd8d6  mov     [r11-408h], rbx
0x1800cd8dd  mov     r12, rdx
0x1800cd8e0  mov     rdi, rcx
0x1800cd8e3  mov     [rsp+498h+var_400], rcx
0x1800cd8eb  mov     [rsp+498h+var_3C8], rcx
0x1800cd8f3  mov     [r11-3C0h], rdx
0x1800cd8fa  mov     [r11-3B8h], rbx
0x1800cd901  lea     r8, aImportsettings_37; "ImportSettingsWork::RestoreBackupSettin"...
0x1800cd908  lea     rdx, aOrchestrator; "Orchestrator"
0x1800cd90f  lea     rcx, [r11-138h]
0x1800cd916  call    sub_18001FAA8
0x1800cd91b  nop
0x1800cd91c  xor     esi, esi
0x1800cd91e  mov     [rsp+498h+var_180], rsi
0x1800cd926  mov     [rsp+498h+var_188], esi
0x1800cd92d  mov     rcx, [r12]
0x1800cd931  mov     rax, [rcx]
0x1800cd934  lea     rdx, [rsp+498h+var_178]
0x1800cd93c  mov     rax, [rax+10h]
0x1800cd940  call    j__guard_dispatch_icall
0x1800cd945  nop
0x1800cd946  lea     r14, [rdi+38h]
0x1800cd94a  mov     [rsp+498h+var_3B0], r14
0x1800cd952  mov     qword ptr [rsp+498h+var_3F8], r14
0x1800cd95a  call    cs:GetCurrentThreadId
0x1800cd960  mov     ebx, eax
0x1800cd962  lea     r13, [r14+4]
0x1800cd966  mov     qword ptr [rsp+498h+var_3E8], r13
0x1800cd96e  mov     ecx, [r13+0]
0x1800cd972  nop
0x1800cd973  cmp     ecx, eax
0x1800cd975  jnz     short loc_1800CD980
0x1800cd977  lea     r15d, [rsi+1]
0x1800cd97b  add     [r14], r15d
0x1800cd97e  jmp     short loc_1800CD996
0x1800cd980  lea     rcx, [r14+8]
0x1800cd984  call    sub_180087970
0x1800cd989  xchg    ebx, [r13+0]
0x1800cd98d  mov     r15d, 1
0x1800cd993  mov     [r14], r15d
0x1800cd996  xorps   xmm0, xmm0
0x1800cd999  movups  [rsp+498h+FileName], xmm0
0x1800cd9a1  movdqa  xmm1, cs:xmmword_1801685F0
0x1800cd9a9  movdqu  [rsp+498h+var_148], xmm1
0x1800cd9b2  mov     word ptr [rsp+498h+FileName], si
0x1800cd9ba  mov     r8d, 3
0x1800cd9c0  lea     rdx, [rsp+498h+FileName]
0x1800cd9c8  lea     rcx, [rsp+498h+var_178]
0x1800cd9d0  call    sub_180089F34
0x1800cd9d5  mov     [rsp+498h+var_188], eax
0x1800cd9dc  test    eax, eax
0x1800cd9de  js      loc_1800CDB3E
0x1800cd9e4  call    sub_180025A94
0x1800cd9e9  mov     rax, [rax]
0x1800cd9ec  test    byte ptr [rax+20h], 8
0x1800cd9f0  jbe     loc_1800CDAE3
0x1800cd9f6  call    sub_180025A94
0x1800cd9fb  mov     [rsp+498h+var_3D8], rax
0x1800cda03  call    sub_180025A94
0x1800cda08  xorps   xmm0, xmm0
0x1800cda0b  movups  [rsp+498h+var_428], xmm0
0x1800cda10  xorps   xmm1, xmm1
0x1800cda13  movdqu  [rsp+498h+var_418], xmm1
0x1800cda1c  mov     r8d, 41h ; 'A'
0x1800cda22  lea     rdx, aImportsettings_38; "ImportSettingsWork::RestoreBackupSettin"...
0x1800cda29  lea     rcx, [rsp+498h+var_428]
0x1800cda2e  call    sub_18001916C
0x1800cda33  nop
0x1800cda34  lea     r8, [rsp+498h+var_428]
0x1800cda39  lea     rdx, [rsp+498h+var_3A8]
0x1800cda41  call    sub_180038B44
0x1800cda46  nop
0x1800cda47  lea     rcx, [rsp+498h+FileName]
0x1800cda4f  mov     [rsp+498h+var_468], rcx
0x1800cda54  lea     rcx, _guard_check_icall_nop
0x1800cda5b  mov     [rsp+498h+var_460], rcx
0x1800cda60  lea     rcx, sub_18002D830
0x1800cda67  mov     [rsp+498h+var_458], rcx
0x1800cda6c  lea     rdx, [rsp+498h+var_468]
0x1800cda71  mov     rcx, rax
0x1800cda74  call    sub_18001ABF0
0x1800cda79  mov     rbx, rax
0x1800cda7c  xorps   xmm0, xmm0
0x1800cda7f  movups  [rsp+498h+var_448], xmm0
0x1800cda84  xorps   xmm1, xmm1
0x1800cda87  movdqu  [rsp+498h+var_438], xmm1
0x1800cda8d  mov     r8d, 0Ch
0x1800cda93  lea     rdx, aOrchestrator; "Orchestrator"
0x1800cda9a  lea     rcx, [rsp+498h+var_448]
0x1800cda9f  call    sub_18001916C
0x1800cdaa4  nop
0x1800cdaa5  mov     r9, rbx
0x1800cdaa8  lea     r8, [rsp+498h+var_448]
0x1800cdaad  mov     edx, 8
0x1800cdab2  mov     rcx, [rsp+498h+var_3D8]
0x1800cdaba  call    sub_180038800
0x1800cdabf  nop
0x1800cdac0  lea     rcx, [rsp+498h+var_448]
0x1800cdac5  call    sub_180028810
0x1800cdaca  nop
0x1800cdacb  lea     rcx, [rsp+498h+var_3A8]
0x1800cdad3  call    sub_180020DCC
0x1800cdad8  nop
0x1800cdad9  lea     rcx, [rsp+498h+var_428]
0x1800cdade  call    sub_180028810
0x1800cdae3  xor     r8d, r8d
0x1800cdae6  xor     edx, edx
0x1800cdae8  lea     rcx, [rsp+498h+FileName]; lpFileName
0x1800cdaf0  call    sub_1800453AC
0x1800cdaf5  nop
0x1800cdaf6  jmp     loc_1800CDC4F
0x1800cdafb  xor     esi, esi
0x1800cdafd  lea     r15d, [rsi+1]
0x1800cdb01  mov     rdi, [rsp+498h+var_3C8]
0x1800cdb09  mov     [rsp+498h+var_400], rdi
0x1800cdb11  mov     r12, [rsp+498h+var_3C0]
0x1800cdb19  mov     rax, [rsp+498h+var_3B8]
0x1800cdb21  mov     [rsp+498h+var_408], rax
0x1800cdb29  mov     r14, [rsp+498h+var_3B0]
0x1800cdb31  mov     r13, qword ptr [rsp+498h+var_3E8]
0x1800cdb39  jmp     loc_1800CDC4F
0x1800cdb3e  cmp     eax, 80070002h
0x1800cdb43  jz      loc_1800CDC48
0x1800cdb49  call    sub_180025A94
0x1800cdb4e  mov     rax, [rax]
0x1800cdb51  test    byte ptr [rax+20h], 8
0x1800cdb55  jbe     loc_1800CDC4F
0x1800cdb5b  call    sub_180025A94
0x1800cdb60  mov     rdi, rax
0x1800cdb63  call    sub_180025A94
0x1800cdb68  xorps   xmm0, xmm0
0x1800cdb6b  movups  [rsp+498h+var_448], xmm0
0x1800cdb70  xorps   xmm1, xmm1
0x1800cdb73  movdqu  [rsp+498h+var_438], xmm1
0x1800cdb79  mov     r8d, 52h ; 'R'
0x1800cdb7f  lea     rdx, aImportsettings_39; "ImportSettingsWork::RestoreBackupSettin"...
0x1800cdb86  lea     rcx, [rsp+498h+var_448]
0x1800cdb8b  call    sub_18001916C
0x1800cdb90  nop
0x1800cdb91  lea     r8, [rsp+498h+var_448]
0x1800cdb96  lea     rdx, [rsp+498h+var_3A8]
0x1800cdb9e  call    sub_180038B44
0x1800cdba3  nop
0x1800cdba4  lea     rcx, [rsp+498h+var_178]
0x1800cdbac  mov     [rsp+498h+var_468], rcx
0x1800cdbb1  lea     rcx, _guard_check_icall_nop
0x1800cdbb8  mov     [rsp+498h+var_460], rcx
0x1800cdbbd  lea     rcx, sub_180018450
0x1800cdbc4  mov     [rsp+498h+var_458], rcx
0x1800cdbc9  lea     rdx, [rsp+498h+var_468]
0x1800cdbce  mov     rcx, rax
0x1800cdbd1  call    sub_18001ABF0
0x1800cdbd6  mov     rbx, rax
0x1800cdbd9  xorps   xmm0, xmm0
0x1800cdbdc  movups  [rsp+498h+var_428], xmm0
0x1800cdbe1  xorps   xmm1, xmm1
0x1800cdbe4  movdqu  [rsp+498h+var_418], xmm1
0x1800cdbed  mov     r8d, 0Ch
0x1800cdbf3  lea     rdx, aOrchestrator; "Orchestrator"
0x1800cdbfa  lea     rcx, [rsp+498h+var_428]
0x1800cdbff  call    sub_18001916C
0x1800cdc04  nop
0x1800cdc05  mov     r9, rbx
0x1800cdc08  lea     r8, [rsp+498h+var_428]
0x1800cdc0d  mov     edx, 8
0x1800cdc12  mov     rcx, rdi
0x1800cdc15  call    sub_180038800
0x1800cdc1a  nop
0x1800cdc1b  lea     rcx, [rsp+498h+var_428]
0x1800cdc20  call    sub_180028810
0x1800cdc25  nop
0x1800cdc26  lea     rcx, [rsp+498h+var_3A8]
0x1800cdc2e  call    sub_180020DCC
0x1800cdc33  nop
0x1800cdc34  lea     rcx, [rsp+498h+var_448]
0x1800cdc39  call    sub_180028810
0x1800cdc3e  mov     rdi, [rsp+498h+var_400]
0x1800cdc46  jmp     short loc_1800CDC4F
0x1800cdc48  mov     [rsp+498h+var_188], esi
0x1800cdc4f  lea     rbx, _guard_check_icall_nop
0x1800cdc56  cmp     [rsp+498h+var_188], esi
0x1800cdc5d  jl      loc_1800CDFE2
0x1800cdc63  mov     r8d, r15d
0x1800cdc66  lea     rdx, [rsp+498h+var_178]
0x1800cdc6e  lea     rcx, [rsp+498h+var_B8]
0x1800cdc76  call    sub_180088728
0x1800cdc7b  nop
0x1800cdc7c  mov     rcx, [r12]
0x1800cdc80  mov     rax, [rcx]
0x1800cdc83  mov     r8, [rdi+0B8h]
0x1800cdc8a  lea     rdx, [rsp+498h+var_B8]
0x1800cdc92  mov     rax, [rax+38h]
0x1800cdc96  call    j__guard_dispatch_icall
0x1800cdc9b  lea     rcx, [rsp+498h+var_B8]
0x1800cdca3  call    sub_1800DD884
0x1800cdca8  mov     rdx, [rsp+498h+var_68]
0x1800cdcb0  mov     edx, [rdx+1E0h]
0x1800cdcb6  lea     rcx, [rsp+498h+var_B8]
0x1800cdcbe  call    sub_18008B18C
0x1800cdcc3  mov     [rsp+498h+var_188], eax
0x1800cdcca  lea     rcx, [rsp+498h+var_B8]
0x1800cdcd2  call    sub_18008925C
0x1800cdcd7  cmp     [rsp+498h+var_188], esi
0x1800cdcde  jl      loc_1800CDFE2
0x1800cdce4  call    sub_180025918
0x1800cdce9  mov     rcx, rax
0x1800cdcec  mov     edi, 2
0x1800cdcf1  mov     dword ptr [rsp+498h+var_180], edi
0x1800cdcf8  mov     dword ptr [rsp+498h+var_180+4], edi
0x1800cdcff  mov     rax, [rax+4BB0h]
0x1800cdd06  test    rax, rax
0x1800cdd09  jz      short loc_1800CDD41
0x1800cdd0b  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800cdd0f  add     rcx, 4BB8h
0x1800cdd16  lea     r9, [rsp+498h+var_180]
0x1800cdd1e  lea     r8, [rsp+498h+var_178]
0x1800cdd26  mov     edx, edi
0x1800cdd28  mov     rax, [rax+8]
0x1800cdd2c  call    j__guard_dispatch_icall
0x1800cdd31  test    al, al
0x1800cdd33  jz      short loc_1800CDD41
0x1800cdd35  mov     dword ptr [rsp+498h+var_180], esi
0x1800cdd3c  jmp     loc_1800CDE64
0x1800cdd41  call    sub_180025A94
0x1800cdd46  mov     rax, [rax]
0x1800cdd49  test    [rax+20h], r15b
0x1800cdd4d  jbe     loc_1800CDE64
0x1800cdd53  call    sub_180025A94
0x1800cdd58  mov     rdi, rax
0x1800cdd5b  call    sub_180025A94
0x1800cdd60  xorps   xmm0, xmm0
0x1800cdd63  movups  [rsp+498h+var_448], xmm0
0x1800cdd68  xorps   xmm1, xmm1
0x1800cdd6b  movdqu  [rsp+498h+var_438], xmm1
0x1800cdd71  mov     r8d, 6Dh ; 'm'
0x1800cdd77  lea     rdx, aImportsettings_40; "ImportSettingsWork::RestoreBackupSettin"...
0x1800cdd7e  lea     rcx, [rsp+498h+var_448]
0x1800cdd83  call    sub_18001916C
0x1800cdd88  nop
0x1800cdd89  lea     r8, [rsp+498h+var_448]
0x1800cdd8e  lea     rdx, [rsp+498h+var_3A8]
0x1800cdd96  call    sub_180038B44
0x1800cdd9b  nop
0x1800cdd9c  lea     rcx, [rsp+498h+var_178]
0x1800cdda4  mov     [rsp+498h+var_468], rcx
0x1800cdda9  mov     [rsp+498h+var_460], rbx
0x1800cddae  lea     rcx, sub_180018450
0x1800cddb5  mov     [rsp+498h+var_458], rcx
0x1800cddba  lea     rdx, [rsp+498h+var_468]
0x1800cddbf  mov     rcx, rax
0x1800cddc2  call    sub_18001ABF0
0x1800cddc7  lea     rcx, [rsp+498h+var_180]
0x1800cddcf  mov     [rsp+498h+var_468], rcx
0x1800cddd4  lea     rcx, _guard_check_icall_nop
0x1800cdddb  mov     [rsp+498h+var_460], rcx
0x1800cdde0  lea     rcx, sub_18001AB60
0x1800cdde7  mov     [rsp+498h+var_458], rcx
0x1800cddec  lea     rdx, [rsp+498h+var_468]
0x1800cddf1  mov     rcx, rax
0x1800cddf4  call    sub_18001ABF0
0x1800cddf9  mov     rbx, rax
0x1800cddfc  xorps   xmm0, xmm0
0x1800cddff  movups  [rsp+498h+var_428], xmm0
0x1800cde04  xorps   xmm1, xmm1
0x1800cde07  movdqu  [rsp+498h+var_418], xmm1
0x1800cde10  mov     r8d, 0Ch
0x1800cde16  lea     rdx, aOrchestrator; "Orchestrator"
0x1800cde1d  lea     rcx, [rsp+498h+var_428]
0x1800cde22  call    sub_18001916C
0x1800cde27  nop
0x1800cde28  mov     r9, rbx
0x1800cde2b  lea     r8, [rsp+498h+var_428]
0x1800cde30  mov     edx, r15d
0x1800cde33  mov     rcx, rdi
0x1800cde36  call    sub_180038800
0x1800cde3b  nop
0x1800cde3c  lea     rcx, [rsp+498h+var_428]
0x1800cde41  call    sub_180028810
0x1800cde46  nop
0x1800cde47  lea     rcx, [rsp+498h+var_3A8]
0x1800cde4f  call    sub_180020DCC
0x1800cde54  nop
0x1800cde55  lea     rcx, [rsp+498h+var_448]
0x1800cde5a  call    sub_180028810
0x1800cde5f  mov     edi, 2
0x1800cde64  lea     rbx, _guard_check_icall_nop
0x1800cde6b  call    sub_180025918
  ... truncated ...
```

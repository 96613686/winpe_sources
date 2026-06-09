# ImmersiveContextMenuHelper::_GetRenderingDataForMenuItem(DPIToPPIHelpers::ScaleType,tagMENUITEMINFOW,ushort const *,tagPOINT *,CSimplePointerArrayNewMem<ContextMenuRenderingData,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>> &,ContextMenuRenderingData *,ImmersiveContextMenuOptions,ContextMenuRenderingData * *)

- ea: `0x18006c078`
- end: `0x18006c262`
- name: `?_GetRenderingDataForMenuItem@ImmersiveContextMenuHelper@@YAJW4ScaleType@DPIToPPIHelpers@@UtagMENUITEMINFOW@@PEBGPEAUtagPOINT@@AEAV?$CSimplePointerArrayNewMem@UContextMenuRenderingData@@V?$CSimpleArrayStandardCompareHelper@PEAUContextMenuRenderingData@@@@@@PEAUContextMenuRenderingData@@W4ImmersiveContextMenuOptions@@PEAPEAU7@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006b3f8`

## callees

- `0x1800116c0`
- `0x180046b0c`
- `0x18005e99c`
- `0x18006beb8`
- `0x18006c078`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromPoint` at `0x18006c18c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromPoint` at `0x18006c18c`
- `api-ms-win-shcore-scaling-l1-1-1!GetDpiForMonitor` at `0x18006c1ab`
- `api-ms-win-shcore-scaling-l1-1-1!GetDpiForMonitor` at `0x18006c1ab`
- `GDI32!DeleteObject` at `0x18006c11d`
- `GDI32!DeleteObject` at `0x18006c11d`

## pseudocode

```c
__int64 __fastcall ImmersiveContextMenuHelper::_GetRenderingDataForMenuItem(
        int a1,
        __int64 a2,
        _WORD *a3,
        POINT *a4,
        _QWORD *a5,
        __int64 a6,
        char a7,
        int **a8)
{
  int **v8; // r15
  int *v13; // rax
  int *v14; // rbx
  unsigned int v15; // edx
  int v16; // esi
  void *v17; // rcx
  int v18; // eax
  POINT v19; // rcx
  HMONITOR v20; // rax
  HWND v21; // rcx
  int v22; // edx
  int *v23; // rax
  int v24; // ecx
  int v26; // [rsp+20h] [rbp-48h] BYREF
  int v27; // [rsp+24h] [rbp-44h] BYREF
  int v28[16]; // [rsp+28h] [rbp-40h] BYREF

  v8 = a8;
  *a8 = 0;
  v13 = (int *)operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
  v14 = v13;
  if ( v13 )
  {
    *(_QWORD *)v13 = 0;
    *((_QWORD *)v13 + 1) = 0;
    *((_QWORD *)v13 + 2) = 0;
    v13[6] = 0;
    v13[7] = 181;
    *((_QWORD *)v13 + 4) = 0;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    v13[14] = 0;
    *((_QWORD *)v13 + 10) = 0;
    v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            (__int64)v13,
            a3,
            0xFFFFFFFFFFFFFFFFuLL);
    if ( v16 < 0 )
    {
      ContextMenuRenderingData::`scalar deleting destructor'((ContextMenuRenderingData *)v14, v15);
    }
    else
    {
      if ( a1 == 1 )
      {
        v17 = *(void **)(a2 + 72);
        v14[7] = v17 != 0 ? 77 : -1;
        DeleteObject(v17);
      }
      else
      {
        *((_QWORD *)v14 + 4) = *(_QWORD *)(a2 + 72);
        v14[7] = -1;
      }
      *((_QWORD *)v14 + 5) = *(_QWORD *)(a2 + 32);
      *((_QWORD *)v14 + 6) = *(_QWORD *)(a2 + 40);
      if ( a6 )
      {
        v18 = *(_DWORD *)(a6 + 64);
      }
      else if ( a5[1] )
      {
        v18 = *(_DWORD *)(*(_QWORD *)*a5 + 64LL);
      }
      else
      {
        if ( a4 )
        {
          v19 = *a4;
        }
        else
        {
          a8 = 0;
          v19 = 0;
        }
        v20 = MonitorFromPoint(v19, 2u);
        v26 = 0;
        v27 = 0;
        if ( (int)GetDpiForMonitor(v20, 0, &v26, &v27) >= 0 )
        {
          v18 = v26;
        }
        else
        {
          LODWORD(a8) = 0;
          SHComputeDPI(v21, (int *)&a8, v28);
          v18 = (int)a8;
        }
      }
      v22 = *(_DWORD *)(a2 + 8);
      v14[16] = v18;
      v23 = v14 + 6;
      if ( (v22 & 0x800) != 0 )
      {
        *v23 = 2048;
        v24 = 2560;
      }
      else if ( *(_QWORD *)(a2 + 24) )
      {
        *v23 = 16;
        v24 = 528;
      }
      else
      {
        *v23 = 0;
        v24 = 512;
      }
      if ( (v22 & 0x200) != 0 )
        *v23 = v24;
      *((_BYTE *)v14 + 68) = byte_180091FF1;
      v14[14] = 0;
      *((_BYTE *)v14 + 69) = (a7 & 8) != 0;
      v14[15] = a1;
      *v8 = v14;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18006c078  push    rbx
0x18006c07a  push    rbp
0x18006c07b  push    rsi
0x18006c07c  push    rdi
0x18006c07d  push    r12
0x18006c07f  push    r14
0x18006c081  push    r15
0x18006c083  sub     rsp, 30h
0x18006c087  mov     r15, [rsp+68h+arg_38]
0x18006c08f  xor     r12d, r12d
0x18006c092  mov     rdi, rdx
0x18006c095  mov     ebp, ecx
0x18006c097  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006c09e  mov     r14, r9
0x18006c0a1  mov     rsi, r8
0x18006c0a4  lea     ecx, [r12+58h]; unsigned __int64
0x18006c0a9  mov     [r15], r12
0x18006c0ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006c0b1  mov     rbx, rax
0x18006c0b4  test    rax, rax
0x18006c0b7  jz      loc_18006C24C
0x18006c0bd  mov     [rax], r12
0x18006c0c0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006c0c4  mov     [rax+8], r12
0x18006c0c8  mov     rdx, rsi
0x18006c0cb  mov     [rax+10h], r12
0x18006c0cf  mov     rcx, rax
0x18006c0d2  mov     [rax+18h], r12d
0x18006c0d6  mov     dword ptr [rax+1Ch], 0B5h
0x18006c0dd  mov     [rax+20h], r12
0x18006c0e1  mov     [rax+28h], r12
0x18006c0e5  mov     [rax+30h], r12
0x18006c0e9  mov     [rax+38h], r12d
0x18006c0ed  mov     [rax+50h], r12
0x18006c0f1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18006c0f6  mov     esi, eax
0x18006c0f8  test    eax, eax
0x18006c0fa  js      loc_18006C242
0x18006c100  cmp     ebp, 1
0x18006c103  jnz     short loc_18006C125
0x18006c105  mov     rcx, [rdi+48h]; ho
0x18006c109  mov     rdx, rcx
0x18006c10c  neg     rdx
0x18006c10f  sbb     r8d, r8d
0x18006c112  and     r8d, 4Eh
0x18006c116  dec     r8d
0x18006c119  mov     [rbx+1Ch], r8d
0x18006c11d  call    cs:__imp_DeleteObject
0x18006c123  jmp     short loc_18006C134
0x18006c125  mov     rax, [rdi+48h]
0x18006c129  mov     [rbx+20h], rax
0x18006c12d  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x18006c134  mov     rax, [rdi+20h]
0x18006c138  mov     [rbx+28h], rax
0x18006c13c  mov     rax, [rdi+28h]
0x18006c140  mov     [rbx+30h], rax
0x18006c144  mov     rax, [rsp+68h+arg_28]
0x18006c14c  test    rax, rax
0x18006c14f  jz      short loc_18006C159
0x18006c151  mov     eax, [rax+40h]
0x18006c154  jmp     loc_18006C1DC
0x18006c159  mov     rax, [rsp+68h+arg_20]
0x18006c161  cmp     [rax+8], r12
0x18006c165  jbe     short loc_18006C172
0x18006c167  mov     rax, [rax]
0x18006c16a  mov     rcx, [rax]
0x18006c16d  mov     eax, [rcx+40h]
0x18006c170  jmp     short loc_18006C1DC
0x18006c172  test    r14, r14
0x18006c175  jz      short loc_18006C17C
0x18006c177  mov     rcx, [r14]
0x18006c17a  jmp     short loc_18006C187
0x18006c17c  mov     [rsp+68h+arg_38], r12
0x18006c184  mov     rcx, r12; pt
0x18006c187  mov     edx, 2; dwFlags
0x18006c18c  call    cs:__imp_MonitorFromPoint
0x18006c192  lea     r9, [rsp+68h+var_44]
0x18006c197  mov     [rsp+68h+var_48], r12d
0x18006c19c  mov     rcx, rax
0x18006c19f  mov     [rsp+68h+var_44], r12d
0x18006c1a4  lea     r8, [rsp+68h+var_48]
0x18006c1a9  xor     edx, edx
0x18006c1ab  call    cs:__imp_GetDpiForMonitor
0x18006c1b1  test    eax, eax
0x18006c1b3  jns     short loc_18006C1D8
0x18006c1b5  lea     r8, [rsp+68h+var_40]; int *
0x18006c1ba  mov     dword ptr [rsp+68h+arg_38], r12d
0x18006c1c2  lea     rdx, [rsp+68h+arg_38]; int *
0x18006c1ca  call    ?SHComputeDPI@@YAXPEAUHWND__@@PEAH1@Z; SHComputeDPI(HWND__ *,int *,int *)
0x18006c1cf  mov     eax, dword ptr [rsp+68h+arg_38]
0x18006c1d6  jmp     short loc_18006C1DC
0x18006c1d8  mov     eax, [rsp+68h+var_48]
0x18006c1dc  mov     edx, [rdi+8]
0x18006c1df  mov     ecx, 800h
0x18006c1e4  mov     [rbx+40h], eax
0x18006c1e7  mov     r8d, 200h
0x18006c1ed  lea     rax, [rbx+18h]
0x18006c1f1  test    ecx, edx
0x18006c1f3  jz      short loc_18006C1FE
0x18006c1f5  mov     [rax], ecx
0x18006c1f7  mov     ecx, 0A00h
0x18006c1fc  jmp     short loc_18006C217
0x18006c1fe  cmp     [rdi+18h], r12
0x18006c202  jz      short loc_18006C211
0x18006c204  mov     dword ptr [rax], 10h
0x18006c20a  mov     ecx, 210h
0x18006c20f  jmp     short loc_18006C217
0x18006c211  mov     [rax], r12d
0x18006c214  mov     ecx, r8d
0x18006c217  test    r8d, edx
0x18006c21a  jz      short loc_18006C21E
0x18006c21c  mov     [rax], ecx
0x18006c21e  mov     al, cs:byte_180091FF1
0x18006c224  mov     [rbx+44h], al
0x18006c227  mov     eax, dword ptr [rsp+68h+arg_30]
0x18006c22e  shr     eax, 3
0x18006c231  and     al, 1
0x18006c233  mov     [rbx+38h], r12d
0x18006c237  mov     [rbx+45h], al
0x18006c23a  mov     [rbx+3Ch], ebp
0x18006c23d  mov     [r15], rbx
0x18006c240  jmp     short loc_18006C251
0x18006c242  mov     rcx, rbx; this
0x18006c245  call    ??_GContextMenuRenderingData@@QEAAPEAXI@Z; ContextMenuRenderingData::`scalar deleting destructor'(uint)
0x18006c24a  jmp     short loc_18006C251
0x18006c24c  mov     esi, 8007000Eh
0x18006c251  mov     eax, esi
0x18006c253  add     rsp, 30h
0x18006c257  pop     r15
0x18006c259  pop     r14
0x18006c25b  pop     r12
0x18006c25d  pop     rdi
0x18006c25e  pop     rsi
0x18006c25f  pop     rbp
0x18006c260  pop     rbx
0x18006c261  retn
```

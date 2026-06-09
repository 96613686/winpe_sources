# DdcDrivesHelper::GetDrivesInfo(std::vector<std::unique_ptr<VolInfo,std::default_delete<VolInfo>>,std::allocator<std::unique_ptr<VolInfo,std::default_delete<VolInfo>>>> &)

- ea: `0x180021f0c`
- end: `0x180022238`
- name: `?GetDrivesInfo@DdcDrivesHelper@@CAJAEAV?$vector@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@@2@@std@@@Z`
- size: `812`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18002166c`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x180002fe4`
- `0x1800032b8`
- `0x1800050b8`
- `0x18001416c`
- `0x180020a48`
- `0x180020bfc`
- `0x180021afc`
- `0x180021f0c`

## import_xrefs

- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x18002208d`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x18002208d`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x180022040`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x180022040`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageInstanceCount` at `0x180021fbf`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageInstanceCount` at `0x180021fbf`
- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x180021f63`
- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x180021f63`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x1800221dd`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x1800221dd`

## string_xrefs

- `0x180022208`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdriveshelper.cpp`
- `0x1800221f4`: `CBR(!!IsOpenStorageTypeSearchPresent())`
- `0x180021f7c`: `CHR(OpenStorageTypeSearch(&phContext))`

## pseudocode

```c
__int64 __fastcall DdcDrivesHelper::GetDrivesInfo(__int64 *a1)
{
  int v2; // edx
  int v3; // ecx
  int v4; // edx
  int v5; // ecx
  int v6; // ebx
  __int64 i; // r14
  unsigned int v8; // esi
  unsigned int j; // edi
  _OWORD *v10; // rax
  int v11; // edx
  int v12; // ecx
  _OWORD *v13; // rbx
  _OWORD *v14; // rcx
  char *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  void *v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v22[2]; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szVolumeMountPoint[262]; // [rsp+74h] [rbp-8Ch] BYREF
  int v27; // [rsp+280h] [rbp+180h]
  __int128 v28; // [rsp+294h] [rbp+194h]
  char v29; // [rsp+2B0h] [rbp+1B0h] BYREF

  v22[0] = 0;
  v22[1] = 2;
  if ( (unsigned __int8)IsOpenStorageTypeSearchPresent() )
  {
    v21 = 0;
    v6 = OpenStorageTypeSearch(&v21);
    if ( v6 >= 0 )
    {
      for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
      {
        v8 = v22[i];
        if ( v8 == 2 )
          break;
        v19 = 0;
        if ( (int)GetStorageInstanceCount(v8, &v19) >= 0 )
        {
          for ( j = 0; j < v19; ++j )
          {
            v10 = operator new(0x250u, (const struct std::nothrow_t *)&std::nothrow);
            v13 = v10;
            if ( !v10 )
            {
              v6 = -2147024882;
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v12,
                  v11,
                  -2147024882,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                  207,
                  "CPR(pInfo)");
              return (unsigned int)v6;
            }
            memset_0(v10, 0, 0x250u);
            v20 = v13;
            memset_0(szVolumeMountPoint, 0, 0x454u);
            v23 = 0;
            v24 = 0;
            v25 = 1112;
            if ( (int)GetStorageDeviceInfo(v8, j, &v25) >= 0
              && !v27
              && (int)SelectStorageVolumeEx(v21, v8, j, 0, 0, 0, &v23, &v24) >= 0 )
            {
              *v13 = v28;
              *((_DWORD *)v13 + 4) = v8;
              *((_DWORD *)v13 + 5) = j;
              v14 = (_OWORD *)((char *)v13 + 24);
              v15 = &v29;
              v16 = 4;
              do
              {
                *v14 = *(_OWORD *)v15;
                v14[1] = *((_OWORD *)v15 + 1);
                v14[2] = *((_OWORD *)v15 + 2);
                v14[3] = *((_OWORD *)v15 + 3);
                v14[4] = *((_OWORD *)v15 + 4);
                v14[5] = *((_OWORD *)v15 + 5);
                v14[6] = *((_OWORD *)v15 + 6);
                v14[7] = *((_OWORD *)v15 + 7);
                v14 += 8;
                v15 += 128;
                --v16;
              }
              while ( v16 );
              *(_QWORD *)v14 = *(_QWORD *)v15;
              *((_QWORD *)v13 + 68) = 107374182 * (v23 / 0x6666666);
              *((_QWORD *)v13 + 69) = 107374182 * (v24 / 0x6666666);
              if ( (int)DdcDrivesHelper::GetBitLockerInfoForVolume(szVolumeMountPoint, (struct VolInfo *)v13) >= 0 )
              {
                v17 = a1[1];
                if ( v17 == a1[2] )
                  std::vector<std::unique_ptr<VolInfo>>::_Emplace_reallocate<std::unique_ptr<VolInfo>>(
                    a1,
                    v17,
                    (__int64 *)&v20);
                else
                  std::vector<std::unique_ptr<DisplayInfo>>::_Emplace_back_with_unused_capacity<std::unique_ptr<DisplayInfo>>(
                    (__int64)a1,
                    (__int64 *)&v20);
              }
            }
            std::unique_ptr<VolInfo>::~unique_ptr<VolInfo>(&v20);
          }
        }
      }
      return (unsigned int)CloseFindStorageSearch(&v21);
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        v6,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
        194,
        "CHR(OpenStorageTypeSearch(&phContext))");
    }
  }
  else
  {
    v6 = 1;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        1,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
        191,
        "CBR(!!IsOpenStorageTypeSearchPresent())");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180021f0c  push    rbp
0x180021f0e  push    rbx
0x180021f0f  push    rsi
0x180021f10  push    rdi
0x180021f11  push    r14
0x180021f13  push    r15
0x180021f15  lea     rbp, [rsp-3E8h]
0x180021f1d  sub     rsp, 4E8h
0x180021f24  mov     rax, cs:__security_cookie
0x180021f2b  xor     rax, rsp
0x180021f2e  mov     [rbp+410h+var_40], rax
0x180021f35  mov     r15, rcx
0x180021f38  mov     [rsp+510h+var_4B8], 0
0x180021f40  mov     [rsp+510h+var_4B4], 2
0x180021f48  call    IsOpenStorageTypeSearchPresent
0x180021f4d  test    al, al
0x180021f4f  jz      loc_1800221E7
0x180021f55  mov     [rsp+510h+var_4C0], 0
0x180021f5e  lea     rcx, [rsp+510h+var_4C0]
0x180021f63  call    cs:__imp_OpenStorageTypeSearch
0x180021f69  mov     ebx, eax
0x180021f6b  test    eax, eax
0x180021f6d  jns     short loc_180021F95
0x180021f6f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021f76  jz      loc_180022217
0x180021f7c  lea     rax, aChrOpenstorage; "CHR(OpenStorageTypeSearch(&phContext))"
0x180021f83  mov     [rsp+510h+var_4E8], rax
0x180021f88  mov     dword ptr [rsp+510h+var_4F0], 0C2h
0x180021f90  jmp     loc_180022208
0x180021f95  xor     r14d, r14d
0x180021f98  cmp     r14d, 2
0x180021f9c  jnb     loc_1800221D8
0x180021fa2  mov     esi, [rsp+r14*4+510h+var_4B8]
0x180021fa7  cmp     esi, 2
0x180021faa  jz      loc_1800221D8
0x180021fb0  mov     [rsp+510h+var_4D0], 0
0x180021fb8  lea     rdx, [rsp+510h+var_4D0]
0x180021fbd  mov     ecx, esi
0x180021fbf  call    cs:__imp_GetStorageInstanceCount
0x180021fc5  test    eax, eax
0x180021fc7  js      loc_1800221AC
0x180021fcd  xor     edi, edi
0x180021fcf  cmp     edi, [rsp+510h+var_4D0]
0x180021fd3  jnb     loc_1800221AC
0x180021fd9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021fe0  mov     ecx, 250h; unsigned __int64
0x180021fe5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021fea  mov     rbx, rax
0x180021fed  test    rax, rax
0x180021ff0  jz      loc_1800221B4
0x180021ff6  xor     edx, edx; Val
0x180021ff8  mov     r8d, 250h; Size
0x180021ffe  mov     rcx, rax; void *
0x180022001  call    memset_0
0x180022006  mov     [rsp+510h+var_4C8], rbx
0x18002200b  xor     edx, edx; Val
0x18002200d  mov     r8d, 454h; Size
0x180022013  lea     rcx, [rsp+510h+szVolumeMountPoint]; void *
0x180022018  call    memset_0
0x18002201d  mov     [rsp+510h+var_4B0], 0
0x180022026  mov     [rsp+510h+var_4A8], 0
0x18002202f  mov     [rsp+510h+var_4A0], 458h
0x180022037  lea     r8, [rsp+510h+var_4A0]
0x18002203c  mov     edx, edi
0x18002203e  mov     ecx, esi
0x180022040  call    cs:__imp_GetStorageDeviceInfo
0x180022046  test    eax, eax
0x180022048  js      loc_18002219B
0x18002204e  cmp     [rbp+410h+var_290], 0
0x180022055  jnz     loc_18002219B
0x18002205b  lea     rax, [rsp+510h+var_4A8]
0x180022060  mov     [rsp+510h+var_4D8], rax
0x180022065  lea     rax, [rsp+510h+var_4B0]
0x18002206a  mov     [rsp+510h+var_4E0], rax
0x18002206f  mov     dword ptr [rsp+510h+var_4E8], 0
0x180022077  mov     [rsp+510h+var_4F0], 0
0x180022080  xor     r9d, r9d
0x180022083  mov     r8d, edi
0x180022086  mov     edx, esi
0x180022088  mov     rcx, [rsp+510h+var_4C0]
0x18002208d  call    cs:__imp_SelectStorageVolumeEx
0x180022093  test    eax, eax
0x180022095  js      loc_18002219B
0x18002209b  movups  xmm0, [rbp+410h+var_27C]
0x1800220a2  movdqu  xmmword ptr [rbx], xmm0
0x1800220a6  mov     [rbx+10h], esi
0x1800220a9  mov     [rbx+14h], edi
0x1800220ac  lea     rcx, [rbx+18h]
0x1800220b0  lea     rax, [rbp+410h+var_260]
0x1800220b7  mov     edx, 4
0x1800220bc  lea     r8d, [rdx+7Ch]
0x1800220c0  movups  xmm0, xmmword ptr [rax]
0x1800220c3  movups  xmmword ptr [rcx], xmm0
0x1800220c6  movups  xmm1, xmmword ptr [rax+10h]
0x1800220ca  movups  xmmword ptr [rcx+10h], xmm1
0x1800220ce  movups  xmm0, xmmword ptr [rax+20h]
0x1800220d2  movups  xmmword ptr [rcx+20h], xmm0
0x1800220d6  movups  xmm1, xmmword ptr [rax+30h]
0x1800220da  movups  xmmword ptr [rcx+30h], xmm1
0x1800220de  movups  xmm0, xmmword ptr [rax+40h]
0x1800220e2  movups  xmmword ptr [rcx+40h], xmm0
0x1800220e6  movups  xmm1, xmmword ptr [rax+50h]
0x1800220ea  movups  xmmword ptr [rcx+50h], xmm1
0x1800220ee  movups  xmm0, xmmword ptr [rax+60h]
0x1800220f2  movups  xmmword ptr [rcx+60h], xmm0
0x1800220f6  movups  xmm1, xmmword ptr [rax+70h]
0x1800220fa  movups  xmmword ptr [rcx+70h], xmm1
0x1800220fe  add     rcx, r8
0x180022101  add     rax, r8
0x180022104  sub     rdx, 1
0x180022108  jnz     short loc_1800220C0
0x18002210a  mov     rax, [rax]
0x18002210d  mov     [rcx], rax
0x180022110  mov     rcx, [rsp+510h+var_4B0]
0x180022115  mov     r8, 4000001400000141h
0x18002211f  mov     rax, r8
0x180022122  mul     rcx
0x180022125  sub     rcx, rdx
0x180022128  shr     rcx, 1
0x18002212b  add     rcx, rdx
0x18002212e  shr     rcx, 1Ah
0x180022132  imul    rax, rcx, 6666666h
0x180022139  mov     [rbx+220h], rax
0x180022140  mov     rcx, [rsp+510h+var_4A8]
0x180022145  mov     rax, r8
0x180022148  mul     rcx
0x18002214b  sub     rcx, rdx
0x18002214e  shr     rcx, 1
0x180022151  add     rcx, rdx
0x180022154  shr     rcx, 1Ah
0x180022158  imul    rax, rcx, 6666666h
0x18002215f  mov     [rbx+228h], rax
0x180022166  mov     rdx, rbx; struct VolInfo *
0x180022169  lea     rcx, [rsp+510h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18002216e  call    ?GetBitLockerInfoForVolume@DdcDrivesHelper@@CAJPEBGPEAUVolInfo@@@Z; DdcDrivesHelper::GetBitLockerInfoForVolume(ushort const *,VolInfo *)
0x180022173  test    eax, eax
0x180022175  js      short loc_18002219B
0x180022177  mov     rdx, [r15+8]
0x18002217b  mov     rcx, r15
0x18002217e  cmp     rdx, [r15+10h]
0x180022182  jz      short loc_180022190
0x180022184  lea     rdx, [rsp+510h+var_4C8]
0x180022189  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<DisplayInfo>>::_Emplace_back_with_unused_capacity<std::unique_ptr<DisplayInfo>>(std::unique_ptr<DisplayInfo> &&)
0x18002218e  jmp     short loc_18002219B
0x180022190  lea     r8, [rsp+510h+var_4C8]
0x180022195  call    ??$_Emplace_reallocate@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@@?$vector@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<VolInfo>>::_Emplace_reallocate<std::unique_ptr<VolInfo>>(std::unique_ptr<VolInfo> * const,std::unique_ptr<VolInfo> &&)
0x18002219a  nop
0x18002219b  lea     rcx, [rsp+510h+var_4C8]
0x1800221a0  call    ??1?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<VolInfo>::~unique_ptr<VolInfo>(void)
0x1800221a5  inc     edi
0x1800221a7  jmp     loc_180021FCF
0x1800221ac  inc     r14d
0x1800221af  jmp     loc_180021F98
0x1800221b4  mov     ebx, 8007000Eh
0x1800221b9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800221c0  jz      short loc_180022217
0x1800221c2  lea     rax, aCprPinfo; "CPR(pInfo)"
0x1800221c9  mov     [rsp+510h+var_4E8], rax
0x1800221ce  mov     dword ptr [rsp+510h+var_4F0], 0CFh
0x1800221d6  jmp     short loc_180022208
0x1800221d8  lea     rcx, [rsp+510h+var_4C0]
0x1800221dd  call    cs:__imp_CloseFindStorageSearch
0x1800221e3  mov     ebx, eax
0x1800221e5  jmp     short loc_180022217
0x1800221e7  mov     ebx, 1
0x1800221ec  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bl
0x1800221f2  jz      short loc_180022217
0x1800221f4  lea     rax, aCbrIsopenstora; "CBR(!!IsOpenStorageTypeSearchPresent())"
0x1800221fb  mov     [rsp+510h+var_4E8], rax
0x180022200  mov     dword ptr [rsp+510h+var_4F0], 0BFh
0x180022208  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18002220f  mov     r8d, ebx
0x180022212  call    McTemplateU0dsqs_EventWriteTransfer
0x180022217  mov     eax, ebx
0x180022219  mov     rcx, [rbp+410h+var_40]
0x180022220  xor     rcx, rsp; StackCookie
0x180022223  call    __security_check_cookie
0x180022228  add     rsp, 4E8h
0x18002222f  pop     r15
0x180022231  pop     r14
0x180022233  pop     rdi
0x180022234  pop     rsi
0x180022235  pop     rbx
0x180022236  pop     rbp
0x180022237  retn
```

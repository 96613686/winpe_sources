# CTieredVolume::GetVolumeTierInternalStatistics_ApiHandler(ulong,long *,uchar * *)

- ea: `0x14003e358`
- end: `0x14003e495`
- name: `?GetVolumeTierInternalStatistics_ApiHandler@CTieredVolume@@QEAAJKPEAJPEAPEAE@Z`
- size: `317`
- prototype: `__int64 __fastcall(CTieredVolume *this, int, int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140039de0`

## callees

- `0x140002323`
- `0x140002db0`
- `0x14000b7f8`
- `0x14003e358`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003e383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003e383`

## pseudocode

```c
__int64 __fastcall CTieredVolume::GetVolumeTierInternalStatistics_ApiHandler(
        CTieredVolume *this,
        int a2,
        int *a3,
        unsigned __int8 **a4)
{
  __int64 result; // rax
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rbx
  __int64 v10; // rdx
  _OWORD *v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm0

  if ( a2 )
    return ATL::AtlHresultFromWin32(87);
  v8 = (unsigned __int8 *)CoTaskMemAlloc(0x170u);
  v9 = v8;
  if ( v8 )
  {
    memset_0(v8, 0, 0x170u);
    v10 = 2;
    *a3 = 368;
    *a4 = v9;
    v11 = (_OWORD *)((char *)this + 208);
    do
    {
      *(_OWORD *)v9 = *v11;
      *((_OWORD *)v9 + 1) = v11[1];
      *((_OWORD *)v9 + 2) = v11[2];
      *((_OWORD *)v9 + 3) = v11[3];
      *((_OWORD *)v9 + 4) = v11[4];
      *((_OWORD *)v9 + 5) = v11[5];
      *((_OWORD *)v9 + 6) = v11[6];
      v12 = v11[7];
      v11 += 8;
      *((_OWORD *)v9 + 7) = v12;
      v9 += 128;
      --v10;
    }
    while ( v10 );
    *(_OWORD *)v9 = *v11;
    *((_OWORD *)v9 + 1) = v11[1];
    *((_OWORD *)v9 + 2) = v11[2];
    *((_OWORD *)v9 + 3) = v11[3];
    *((_OWORD *)v9 + 4) = v11[4];
    *((_OWORD *)v9 + 5) = v11[5];
    v13 = v11[6];
    result = 0;
    *((_OWORD *)v9 + 6) = v13;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
        (_DWORD)this + 672,
        14);
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x14003e358  push    rbx
0x14003e35a  push    rsi
0x14003e35b  push    rdi
0x14003e35c  push    r14
0x14003e35e  sub     rsp, 38h
0x14003e362  mov     rsi, r9
0x14003e365  mov     r14, r8
0x14003e368  mov     rdi, rcx
0x14003e36b  test    edx, edx
0x14003e36d  jz      short loc_14003E37E
0x14003e36f  mov     ecx, 57h ; 'W'; unsigned int
0x14003e374  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003e379  jmp     loc_14003E48B
0x14003e37e  mov     ecx, 170h; cb
0x14003e383  call    cs:__imp_CoTaskMemAlloc
0x14003e389  mov     rbx, rax
0x14003e38c  test    rax, rax
0x14003e38f  jnz     short loc_14003E3E0
0x14003e391  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e398  lea     rax, WPP_GLOBAL_Control
0x14003e39f  mov     ebx, 8007000Eh
0x14003e3a4  cmp     rcx, rax
0x14003e3a7  jz      short loc_14003E3D9
0x14003e3a9  test    byte ptr [rcx+1Ch], 1
0x14003e3ad  jz      short loc_14003E3D9
0x14003e3af  mov     edx, 2
0x14003e3b4  cmp     [rcx+19h], dl
0x14003e3b7  jb      short loc_14003E3D9
0x14003e3b9  mov     rcx, [rcx+10h]
0x14003e3bd  lea     r9, [rdi+2A0h]
0x14003e3c4  mov     edx, 5Fh ; '_'
0x14003e3c9  mov     [rsp+58h+var_38], ebx
0x14003e3cd  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003e3d4  call    WPP_SF_Zd
0x14003e3d9  mov     eax, ebx
0x14003e3db  jmp     loc_14003E48B
0x14003e3e0  xor     edx, edx; Val
0x14003e3e2  mov     r8d, 170h; Size
0x14003e3e8  mov     rcx, rbx; void *
0x14003e3eb  call    memset_0
0x14003e3f0  mov     edx, 2
0x14003e3f5  mov     dword ptr [r14], 170h
0x14003e3fc  mov     [rsi], rbx
0x14003e3ff  lea     rax, [rdi+0D0h]
0x14003e406  lea     ecx, [rdx+7Eh]
0x14003e409  movups  xmm0, xmmword ptr [rax]
0x14003e40c  movups  xmmword ptr [rbx], xmm0
0x14003e40f  movups  xmm1, xmmword ptr [rax+10h]
0x14003e413  movups  xmmword ptr [rbx+10h], xmm1
0x14003e417  movups  xmm0, xmmword ptr [rax+20h]
0x14003e41b  movups  xmmword ptr [rbx+20h], xmm0
0x14003e41f  movups  xmm1, xmmword ptr [rax+30h]
0x14003e423  movups  xmmword ptr [rbx+30h], xmm1
0x14003e427  movups  xmm0, xmmword ptr [rax+40h]
0x14003e42b  movups  xmmword ptr [rbx+40h], xmm0
0x14003e42f  movups  xmm1, xmmword ptr [rax+50h]
0x14003e433  movups  xmmword ptr [rbx+50h], xmm1
0x14003e437  movups  xmm0, xmmword ptr [rax+60h]
0x14003e43b  movups  xmmword ptr [rbx+60h], xmm0
0x14003e43f  movups  xmm1, xmmword ptr [rax+70h]
0x14003e443  add     rax, rcx
0x14003e446  movups  xmmword ptr [rbx+70h], xmm1
0x14003e44a  add     rbx, rcx
0x14003e44d  sub     rdx, 1
0x14003e451  jnz     short loc_14003E409
0x14003e453  movups  xmm0, xmmword ptr [rax]
0x14003e456  movups  xmmword ptr [rbx], xmm0
0x14003e459  movups  xmm1, xmmword ptr [rax+10h]
0x14003e45d  movups  xmmword ptr [rbx+10h], xmm1
0x14003e461  movups  xmm0, xmmword ptr [rax+20h]
0x14003e465  movups  xmmword ptr [rbx+20h], xmm0
0x14003e469  movups  xmm1, xmmword ptr [rax+30h]
0x14003e46d  movups  xmmword ptr [rbx+30h], xmm1
0x14003e471  movups  xmm0, xmmword ptr [rax+40h]
0x14003e475  movups  xmmword ptr [rbx+40h], xmm0
0x14003e479  movups  xmm1, xmmword ptr [rax+50h]
0x14003e47d  movups  xmmword ptr [rbx+50h], xmm1
0x14003e481  movups  xmm0, xmmword ptr [rax+60h]
0x14003e485  xor     eax, eax
0x14003e487  movups  xmmword ptr [rbx+60h], xmm0
0x14003e48b  add     rsp, 38h
0x14003e48f  pop     r14
0x14003e491  pop     rdi
0x14003e492  pop     rsi
0x14003e493  pop     rbx
0x14003e494  retn
```

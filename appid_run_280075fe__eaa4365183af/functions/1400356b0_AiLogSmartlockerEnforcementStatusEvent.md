# AiLogSmartlockerEnforcementStatusEvent

- ea: `0x1400356b0`
- end: `0x14003597d`
- name: `AiLogSmartlockerEnforcementStatusEvent`
- size: `717`
- prototype: `__int64 __usercall@<rax>(REGHANDLE RegHandle@<rcx>, PCEVENT_DESCRIPTOR EventDescriptor@<rdx>, char, char, char, int, __int64, char, char, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140030620`

## callees

- `0x140001970`
- `0x140006a20`
- `0x1400356b0`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14003591a`
- `ntoskrnl!EtwWrite` at `0x14003591a`

## pseudocode

```c
NTSTATUS __fastcall AiLogSmartlockerEnforcementStatusEvent(
        REGHANDLE RegHandle,
        PCEVENT_DESCRIPTOR EventDescriptor,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        char a5,
        char a6,
        char a7,
        int a8,
        __int64 a9,
        char a10,
        unsigned __int8 a11,
        __int64 a12)
{
  int v12; // ebx
  int v14; // ecx
  int v15; // ecx
  unsigned int v16; // ecx
  const wchar_t *v17; // rax
  NTSTATUS result; // eax
  __int16 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v20; // [rsp+34h] [rbp-CCh] BYREF
  int v21; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v22; // [rsp+3Ch] [rbp-C4h] BYREF
  __int16 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v26; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+88h] [rbp-78h]
  int v30; // [rsp+8Ch] [rbp-74h]
  __int16 *v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+A8h] [rbp-58h]
  int v35; // [rsp+ACh] [rbp-54h]
  char *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  char *v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  char *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  char *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  __int16 *v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  __int64 v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  int *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  __int128 *v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  __int128 *v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  int *v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  int *v56; // [rsp+150h] [rbp+50h]
  __int64 v57; // [rsp+158h] [rbp+58h]
  int *v58; // [rsp+160h] [rbp+60h]
  __int64 v59; // [rsp+168h] [rbp+68h]
  int *v60; // [rsp+170h] [rbp+70h]
  __int64 v61; // [rsp+178h] [rbp+78h]
  int *v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  __int16 *v64; // [rsp+190h] [rbp+90h]
  __int64 v65; // [rsp+198h] [rbp+98h]
  const wchar_t *v66; // [rsp+1A0h] [rbp+A0h]
  __int64 v67; // [rsp+1A8h] [rbp+A8h]

  v12 = (int)a3;
  *(_QWORD *)&UserData.Size = 2;
  v32 = 2;
  v19 = 0;
  v24 = 16;
  v14 = *a3;
  v22 = *a3 >> 1;
  UserData.Ptr = (ULONGLONG)&v22;
  v28 = *((_QWORD *)a3 + 1);
  v31 = &v23;
  v33 = *((_QWORD *)a4 + 1);
  v36 = &a5;
  v38 = &a10;
  v40 = &a6;
  v42 = &a7;
  v44 = &v24;
  v46 = a9;
  v29 = v14;
  v15 = *a4;
  v48 = &v25;
  v25 = a11;
  v21 = 0;
  v20 = 0;
  v30 = 0;
  v23 = v15;
  v34 = v15;
  v35 = 0;
  v37 = 4;
  v39 = 4;
  v41 = 4;
  v43 = 8;
  v45 = 2;
  v47 = 16;
  v49 = 4;
  v51 = 16;
  v53 = 16;
  v55 = 4;
  v57 = 4;
  v59 = 4;
  v61 = 4;
  v63 = 4;
  v65 = 2;
  v26 = 0;
  if ( a11 )
  {
    v16 = *(_DWORD *)(a12 + 56);
    v50 = (__int128 *)(a12 + 16);
    v52 = (__int128 *)(a12 + 32);
    v54 = (int *)(a12 + 4);
    v56 = (int *)(a12 + 8);
    v58 = (int *)(a12 + 12);
    v60 = (int *)(a12 + 48);
    v62 = (int *)(a12 + 52);
    v19 = v16 >> 1;
    v64 = &v19;
    v17 = (const wchar_t *)(a12 + 60);
    v67 = v16;
  }
  else
  {
    v67 = 2;
    v50 = &v26;
    v52 = &v26;
    v54 = &v21;
    v56 = &v21;
    v58 = &v21;
    v60 = &v21;
    v62 = &v21;
    v20 = 1;
    v64 = &v20;
    v17 = L"-";
  }
  v66 = v17;
  result = EtwWrite(RegHandle, EventDescriptor, 0, 0x14u, &UserData);
  if ( result < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    return WPP_SF_ZD(
             WPP_GLOBAL_Control->AttachedDevice,
             18,
             (unsigned int)WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids,
             v12,
             result);
  }
  return result;
}

```

## disassembly

```asm
0x1400356b0  push    rbp
0x1400356b2  push    rbx
0x1400356b3  push    rdi
0x1400356b4  lea     rbp, [rsp-0C0h]
0x1400356bc  sub     rsp, 1C0h
0x1400356c3  mov     rax, cs:__security_cookie
0x1400356ca  xor     rax, rsp
0x1400356cd  mov     [rbp+0D0h+var_20], rax
0x1400356d4  mov     rbx, r8
0x1400356d7  mov     qword ptr [rsp+1D0h+var_160.Size], 2
0x1400356e0  xor     r8d, r8d; ActivityId
0x1400356e3  mov     [rbp+0D0h+var_138], 2
0x1400356eb  mov     edi, 10h
0x1400356f0  mov     [rsp+1D0h+var_1A0], r8w
0x1400356f6  mov     r10, rcx
0x1400356f9  mov     [rsp+1D0h+var_188], di
0x1400356fe  movzx   ecx, word ptr [rbx]
0x140035701  mov     r11, rdx
0x140035704  movzx   edx, [rbp+0D0h+arg_50]
0x14003570b  movzx   eax, cx
0x14003570e  shr     ax, 1
0x140035711  xorps   xmm0, xmm0
0x140035714  mov     [rsp+1D0h+var_194], ax
0x140035719  lea     rax, [rsp+1D0h+var_194]
0x14003571e  mov     [rsp+1D0h+var_160.Ptr], rax
0x140035723  mov     rax, [rbx+8]
0x140035727  mov     [rbp+0D0h+var_150], rax
0x14003572b  lea     rax, [rsp+1D0h+var_190]
0x140035730  mov     [rbp+0D0h+var_140], rax
0x140035734  mov     rax, [r9+8]
0x140035738  mov     [rbp+0D0h+var_130], rax
0x14003573c  lea     rax, [rbp+0D0h+arg_20]
0x140035743  mov     [rbp+0D0h+var_120], rax
0x140035747  lea     rax, [rbp+0D0h+arg_48]
0x14003574e  mov     [rbp+0D0h+var_110], rax
0x140035752  lea     rax, [rbp+0D0h+arg_28]
0x140035759  mov     [rbp+0D0h+var_100], rax
0x14003575d  lea     rax, [rbp+0D0h+arg_30]
0x140035764  mov     [rbp+0D0h+var_F0], rax
0x140035768  lea     rax, [rsp+1D0h+var_188]
0x14003576d  mov     [rbp+0D0h+var_E0], rax
0x140035771  mov     rax, [rbp+0D0h+arg_40]
0x140035778  mov     [rbp+0D0h+var_D0], rax
0x14003577c  lea     rax, [rsp+1D0h+var_180]
0x140035781  mov     [rbp+0D0h+var_148], ecx
0x140035784  movzx   ecx, word ptr [r9]
0x140035788  mov     [rbp+0D0h+var_C0], rax
0x14003578c  mov     [rsp+1D0h+var_180], edx
0x140035790  mov     [rsp+1D0h+var_198], r8d
0x140035795  mov     [rsp+1D0h+var_19C], r8w
0x14003579b  mov     [rbp+0D0h+var_144], r8d
0x14003579f  mov     [rsp+1D0h+var_190], cx
0x1400357a4  mov     [rbp+0D0h+var_128], ecx
0x1400357a7  mov     [rbp+0D0h+var_124], r8d
0x1400357ab  mov     [rbp+0D0h+var_118], 4
0x1400357b3  mov     [rbp+0D0h+var_108], 4
0x1400357bb  mov     [rbp+0D0h+var_F8], 4
0x1400357c3  mov     [rbp+0D0h+var_E8], 8
0x1400357cb  mov     [rbp+0D0h+var_D8], 2
0x1400357d3  mov     [rbp+0D0h+var_C8], rdi
0x1400357d7  mov     [rbp+0D0h+var_B8], 4
0x1400357df  mov     [rbp+0D0h+var_A8], rdi
0x1400357e3  mov     [rbp+0D0h+var_98], rdi
0x1400357e7  mov     [rbp+0D0h+var_88], 4
0x1400357ef  mov     [rbp+0D0h+var_78], 4
0x1400357f7  mov     [rbp+0D0h+var_68], 4
0x1400357ff  mov     [rbp+0D0h+var_58], 4
0x140035807  mov     [rbp+0D0h+var_48], 4
0x140035812  mov     [rbp+0D0h+var_38], 2
0x14003581d  movups  [rsp+1D0h+var_178], xmm0
0x140035822  test    dl, dl
0x140035824  jz      short loc_140035893
0x140035826  mov     rdx, [rbp+0D0h+arg_58]
0x14003582d  mov     dword ptr [rbp+0D0h+var_28+4], r8d
0x140035834  mov     ecx, [rdx+38h]
0x140035837  lea     rax, [rdx+10h]
0x14003583b  mov     [rbp+0D0h+var_B0], rax
0x14003583f  lea     rax, [rdx+20h]
0x140035843  mov     [rbp+0D0h+var_A0], rax
0x140035847  lea     rax, [rdx+4]
0x14003584b  mov     [rbp+0D0h+var_90], rax
0x14003584f  lea     rax, [rdx+8]
0x140035853  mov     [rbp+0D0h+var_80], rax
0x140035857  lea     rax, [rdx+0Ch]
0x14003585b  mov     [rbp+0D0h+var_70], rax
0x14003585f  lea     rax, [rdx+30h]
0x140035863  mov     [rbp+0D0h+var_60], rax
0x140035867  lea     rax, [rdx+34h]
0x14003586b  mov     [rbp+0D0h+var_50], rax
0x140035872  mov     eax, ecx
0x140035874  shr     eax, 1
0x140035876  mov     [rsp+1D0h+var_1A0], ax
0x14003587b  lea     rax, [rsp+1D0h+var_1A0]
0x140035880  mov     [rbp+0D0h+var_40], rax
0x140035887  lea     rax, [rdx+3Ch]
0x14003588b  mov     dword ptr [rbp+0D0h+var_28], ecx
0x140035891  jmp     short loc_1400358FD
0x140035893  lea     rax, [rsp+1D0h+var_178]
0x140035898  mov     [rbp+0D0h+var_28], 2
0x1400358a3  mov     [rbp+0D0h+var_B0], rax
0x1400358a7  lea     rax, [rsp+1D0h+var_178]
0x1400358ac  mov     [rbp+0D0h+var_A0], rax
0x1400358b0  lea     rax, [rsp+1D0h+var_198]
0x1400358b5  mov     [rbp+0D0h+var_90], rax
0x1400358b9  lea     rax, [rsp+1D0h+var_198]
0x1400358be  mov     [rbp+0D0h+var_80], rax
0x1400358c2  lea     rax, [rsp+1D0h+var_198]
0x1400358c7  mov     [rbp+0D0h+var_70], rax
0x1400358cb  lea     rax, [rsp+1D0h+var_198]
0x1400358d0  mov     [rbp+0D0h+var_60], rax
0x1400358d4  lea     rax, [rsp+1D0h+var_198]
0x1400358d9  mov     [rbp+0D0h+var_50], rax
0x1400358e0  mov     eax, 1
0x1400358e5  mov     [rsp+1D0h+var_19C], ax
0x1400358ea  lea     rax, [rsp+1D0h+var_19C]
0x1400358ef  mov     [rbp+0D0h+var_40], rax
0x1400358f6  lea     rax, asc_14000A410; "-"
0x1400358fd  mov     [rbp+0D0h+var_30], rax
0x140035904  mov     r9d, 14h; UserDataCount
0x14003590a  lea     rax, [rsp+1D0h+var_160]
0x14003590f  mov     rdx, r11; EventDescriptor
0x140035912  mov     rcx, r10; RegHandle
0x140035915  mov     [rsp+1D0h+UserData], rax; UserData
0x14003591a  call    cs:__imp_EtwWrite
0x140035921  nop     dword ptr [rax+rax+00h]
0x140035926  test    eax, eax
0x140035928  jns     short loc_140035962
0x14003592a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035931  lea     rdx, WPP_GLOBAL_Control
0x140035938  cmp     rcx, rdx
0x14003593b  jz      short loc_140035962
0x14003593d  test    dword ptr [rcx+2Ch], 200h
0x140035944  jz      short loc_140035962
0x140035946  mov     rcx, [rcx+18h]
0x14003594a  lea     r8, WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids
0x140035951  mov     edx, 12h
0x140035956  mov     dword ptr [rsp+1D0h+UserData], eax
0x14003595a  mov     r9, rbx
0x14003595d  call    WPP_SF_ZD
0x140035962  mov     rcx, [rbp+0D0h+var_20]
0x140035969  xor     rcx, rsp; StackCookie
0x14003596c  call    __security_check_cookie
0x140035971  add     rsp, 1C0h
0x140035978  pop     rdi
0x140035979  pop     rbx
0x14003597a  pop     rbp
0x14003597b  retn
```

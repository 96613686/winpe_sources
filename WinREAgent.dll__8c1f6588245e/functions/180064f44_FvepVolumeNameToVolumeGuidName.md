# FvepVolumeNameToVolumeGuidName

- ea: `0x180064f44`
- end: `0x1800650f8`
- name: `FvepVolumeNameToVolumeGuidName`
- size: `436`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800648b4`

## callees

- `0x180012820`
- `0x180063370`
- `0x180063cf0`
- `0x180063d50`
- `0x180064f44`

## import_xrefs

- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180065069`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180065069`
- `ntdll!RtlSetThreadErrorMode` at `0x180064f84`
- `ntdll!RtlSetThreadErrorMode` at `0x1800650e1`
- `ntdll!RtlSetThreadErrorMode` at `0x180064f84`
- `ntdll!RtlSetThreadErrorMode` at `0x1800650e1`

## pseudocode

```c
__int64 __fastcall FvepVolumeNameToVolumeGuidName(unsigned __int16 *a1, LPWSTR *a2)
{
  HRESULT v4; // ebx
  unsigned __int64 v5; // rsi
  size_t v6; // rcx
  int v7; // eax
  LPWSTR v8; // rdi
  ULONG OldMode; // [rsp+70h] [rbp+40h] BYREF
  size_t pcchLength; // [rsp+80h] [rbp+50h] BYREF
  LPWSTR lpszVolumeName; // [rsp+88h] [rbp+58h]

  pcchLength = 0;
  OldMode = 0;
  lpszVolumeName = 0;
  RtlSetThreadErrorMode(0x10u, &OldMode);
  if ( !a1 )
    goto LABEL_2;
  if ( !a2 )
  {
    v4 = -2147467261;
    goto LABEL_23;
  }
  v4 = 0;
  if ( StringCchLengthW(a1, 0x104u, &pcchLength) < 0 )
    goto LABEL_23;
  if ( pcchLength >= 2 )
  {
    v5 = pcchLength + 2;
    v4 = FveDetectAlloc(2 * (pcchLength + 2));
    if ( v4 >= 0 )
    {
      v4 = StringCchCopyW(0, v5, a1);
      if ( v4 >= 0 )
      {
        v4 = StringCchLengthW(0, 0x104u, &pcchLength);
        if ( v4 >= 0 )
        {
          v6 = pcchLength;
          if ( *(_WORD *)(2 * pcchLength - 2) != 92 )
          {
            *(_WORD *)(2 * pcchLength) = 92;
            pcchLength = v6 + 1;
            *(_WORD *)(2 * (v6 + 1)) = 0;
          }
          v7 = FveDetectAlloc(0x64u);
          v8 = lpszVolumeName;
          v4 = v7;
          if ( v7 >= 0 )
          {
            if ( !GetVolumeNameForVolumeMountPointW(0, lpszVolumeName, 0x32u) )
            {
              FveDetectFree(v8);
              v8 = 0;
            }
            v4 = StringCchLengthW(v8, 0x104u, &pcchLength);
            if ( v4 >= 0 )
            {
              if ( pcchLength >= 2 )
              {
                if ( v8[pcchLength - 1] == 92 )
                  v8[pcchLength - 1] = 0;
                *a2 = v8;
                v8 = 0;
                v4 = 0;
              }
              else
              {
                v4 = -2147024809;
              }
            }
          }
          if ( v8 )
            FveDetectFree(v8);
        }
      }
    }
  }
  else
  {
LABEL_2:
    v4 = -2147024809;
  }
LABEL_23:
  RtlSetThreadErrorMode(OldMode, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180064f44  push    rbp
0x180064f46  push    rbx
0x180064f47  push    rsi
0x180064f48  push    rdi
0x180064f49  push    r12
0x180064f4b  push    r13
0x180064f4d  push    r14
0x180064f4f  mov     rbp, rsp
0x180064f52  sub     rsp, 30h
0x180064f56  mov     r14, rdx
0x180064f59  mov     [rbp+pcchLength], 0
0x180064f61  mov     rdi, rcx
0x180064f64  mov     [rbp+OldMode], 0
0x180064f6b  lea     rdx, [rbp+OldMode]; OldMode
0x180064f6f  mov     [rbp+psz], 0
0x180064f77  mov     ecx, 10h; NewMode
0x180064f7c  mov     [rbp+lpszVolumeName], 0
0x180064f84  call    cs:__imp_RtlSetThreadErrorMode
0x180064f8a  test    rdi, rdi
0x180064f8d  jnz     short loc_180064F99
0x180064f8f  mov     ebx, 80070057h
0x180064f94  jmp     loc_1800650DC
0x180064f99  test    r14, r14
0x180064f9c  jnz     short loc_180064FA8
0x180064f9e  mov     ebx, 80004003h
0x180064fa3  jmp     loc_1800650DC
0x180064fa8  mov     r13d, 104h
0x180064fae  lea     r8, [rbp+pcchLength]; pcchLength
0x180064fb2  mov     edx, r13d; cchMax
0x180064fb5  mov     rcx, rdi; psz
0x180064fb8  xor     ebx, ebx
0x180064fba  call    StringCchLengthW
0x180064fbf  test    eax, eax
0x180064fc1  js      loc_1800650DC
0x180064fc7  mov     rax, [rbp+pcchLength]
0x180064fcb  cmp     rax, 2
0x180064fcf  jb      short loc_180064F8F
0x180064fd1  lea     rsi, [rax+2]
0x180064fd5  lea     rcx, [rsi+rsi]; dwBytes
0x180064fd9  lea     rdx, [rbp+psz]
0x180064fdd  call    FveDetectAlloc
0x180064fe2  mov     ebx, eax
0x180064fe4  test    eax, eax
0x180064fe6  js      loc_1800650CB
0x180064fec  mov     rdx, rsi; unsigned __int64
0x180064fef  mov     r8, rdi; unsigned __int16 *
0x180064ff2  mov     rsi, [rbp+psz]
0x180064ff6  mov     rcx, rsi; unsigned __int16 *
0x180064ff9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180064ffe  mov     ebx, eax
0x180065000  test    eax, eax
0x180065002  js      loc_1800650CF
0x180065008  lea     r8, [rbp+pcchLength]; pcchLength
0x18006500c  mov     edx, r13d; cchMax
0x18006500f  mov     rcx, rsi; psz
0x180065012  call    StringCchLengthW
0x180065017  mov     ebx, eax
0x180065019  test    eax, eax
0x18006501b  js      loc_1800650CF
0x180065021  mov     rcx, [rbp+pcchLength]
0x180065025  mov     r12d, 5Ch ; '\'
0x18006502b  cmp     [rsi+rcx*2-2], r12w
0x180065031  jz      short loc_180065045
0x180065033  mov     [rsi+rcx*2], r12w
0x180065038  inc     rcx
0x18006503b  xor     eax, eax
0x18006503d  mov     [rbp+pcchLength], rcx
0x180065041  mov     [rsi+rcx*2], ax
0x180065045  lea     rdx, [rbp+lpszVolumeName]
0x180065049  mov     ecx, 64h ; 'd'; dwBytes
0x18006504e  call    FveDetectAlloc
0x180065053  mov     rdi, [rbp+lpszVolumeName]
0x180065057  mov     ebx, eax
0x180065059  test    eax, eax
0x18006505b  js      short loc_1800650BC
0x18006505d  mov     r8d, 32h ; '2'; cchBufferLength
0x180065063  mov     rdx, rdi; lpszVolumeName
0x180065066  mov     rcx, rsi; lpszVolumeMountPoint
0x180065069  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18006506f  test    eax, eax
0x180065071  jnz     short loc_180065080
0x180065073  mov     rcx, rdi; lpMem
0x180065076  call    FveDetectFree
0x18006507b  mov     rdi, rsi
0x18006507e  xor     esi, esi
0x180065080  lea     r8, [rbp+pcchLength]; pcchLength
0x180065084  mov     rdx, r13; cchMax
0x180065087  mov     rcx, rdi; psz
0x18006508a  call    StringCchLengthW
0x18006508f  mov     ebx, eax
0x180065091  test    eax, eax
0x180065093  js      short loc_1800650BC
0x180065095  mov     rcx, [rbp+pcchLength]
0x180065099  cmp     rcx, 2
0x18006509d  jnb     short loc_1800650A6
0x18006509f  mov     ebx, 80070057h
0x1800650a4  jmp     short loc_1800650BC
0x1800650a6  cmp     [rdi+rcx*2-2], r12w
0x1800650ac  jnz     short loc_1800650B5
0x1800650ae  xor     eax, eax
0x1800650b0  mov     [rdi+rcx*2-2], ax
0x1800650b5  mov     [r14], rdi
0x1800650b8  xor     edi, edi
0x1800650ba  xor     ebx, ebx
0x1800650bc  test    rdi, rdi
0x1800650bf  jz      short loc_1800650CF
0x1800650c1  mov     rcx, rdi; lpMem
0x1800650c4  call    FveDetectFree
0x1800650c9  jmp     short loc_1800650CF
0x1800650cb  mov     rsi, [rbp+psz]
0x1800650cf  test    rsi, rsi
0x1800650d2  jz      short loc_1800650DC
0x1800650d4  mov     rcx, rsi; lpMem
0x1800650d7  call    FveDetectFree
0x1800650dc  mov     ecx, [rbp+OldMode]; NewMode
0x1800650df  xor     edx, edx; OldMode
0x1800650e1  call    cs:__imp_RtlSetThreadErrorMode
0x1800650e7  mov     eax, ebx
0x1800650e9  add     rsp, 30h
0x1800650ed  pop     r14
0x1800650ef  pop     r13
0x1800650f1  pop     r12
0x1800650f3  pop     rdi
0x1800650f4  pop     rsi
0x1800650f5  pop     rbx
0x1800650f6  pop     rbp
0x1800650f7  retn
```

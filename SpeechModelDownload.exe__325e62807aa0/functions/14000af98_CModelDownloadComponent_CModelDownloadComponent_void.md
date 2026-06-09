# CModelDownloadComponent::CModelDownloadComponent(void)

- ea: `0x14000af98`
- end: `0x14000b049`
- name: `??0CModelDownloadComponent@@QEAA@XZ`
- size: `177`
- prototype: `CModelDownloadComponent *__fastcall(CModelDownloadComponent *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009698`

## callees

- `0x14000af98`

## pseudocode

```c
CModelDownloadComponent *__fastcall CModelDownloadComponent::CModelDownloadComponent(CModelDownloadComponent *this)
{
  __int64 v2; // r8
  __int64 v3; // rcx

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v2 = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 1;
  *((_DWORD *)this + 9) = 1;
  *((_QWORD *)this + 5) = 1;
  *((_DWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 52) = 0;
  *((_DWORD *)this + 6145) = 0;
  *((_QWORD *)this + 3073) = 0;
  *((_QWORD *)this + 3074) = 0;
  *((_DWORD *)this + 6150) = 0;
  *((_WORD *)this + 843) = 0;
  *((_WORD *)this + 1868) = 0;
  *((_WORD *)this + 60) = 0;
  *((_WORD *)this + 321) = 0;
  *((_WORD *)this + 582) = 0;
  *((_WORD *)this + 2129) = 0;
  *((_WORD *)this + 3154) = 0;
  *((_WORD *)this + 3415) = 0;
  *((_WORD *)this + 3676) = 0;
  do
  {
    v3 = 522 * v2++;
    *(_WORD *)((char *)this + v3 + 7874) = 0;
  }
  while ( v2 != 32 );
  return this;
}

```

## disassembly

```asm
0x14000af98  xor     r9d, r9d
0x14000af9b  xorps   xmm0, xmm0
0x14000af9e  mov     [rcx], r9
0x14000afa1  mov     rdx, rcx
0x14000afa4  mov     [rcx+8], r9
0x14000afa8  mov     r8d, r9d
0x14000afab  mov     [rcx+10h], r9
0x14000afaf  mov     [rcx+18h], r9
0x14000afb3  lea     r10d, [r9+1]
0x14000afb7  mov     [rcx+20h], r10d
0x14000afbb  mov     [rcx+24h], r10d
0x14000afbf  mov     [rcx+28h], r10
0x14000afc3  mov     [rcx+30h], r9d
0x14000afc7  movups  xmmword ptr [rcx+34h], xmm0
0x14000afcb  mov     [rcx+6004h], r9d
0x14000afd2  mov     [rcx+6008h], r9
0x14000afd9  mov     [rcx+6010h], r9
0x14000afe0  mov     [rcx+6018h], r9d
0x14000afe7  mov     [rcx+696h], r9w
0x14000afef  mov     [rcx+0E98h], r9w
0x14000aff7  mov     [rcx+78h], r9w
0x14000affc  mov     [rcx+282h], r9w
0x14000b004  mov     [rcx+48Ch], r9w
0x14000b00c  mov     [rcx+10A2h], r9w
0x14000b014  mov     [rcx+18A4h], r9w
0x14000b01c  mov     [rcx+1AAEh], r9w
0x14000b024  mov     [rcx+1CB8h], r9w
0x14000b02c  imul    rcx, r8, 20Ah
0x14000b033  add     r8, r10
0x14000b036  mov     [rcx+rdx+1EC2h], r9w
0x14000b03f  cmp     r8, 20h ; ' '
0x14000b043  jnz     short loc_14000B02C
0x14000b045  mov     rax, rdx
0x14000b048  retn
```

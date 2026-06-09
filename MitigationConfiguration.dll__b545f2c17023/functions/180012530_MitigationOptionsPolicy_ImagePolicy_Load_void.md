# MitigationOptionsPolicy::ImagePolicy::Load(void)

- ea: `0x180012530`
- end: `0x18001274b`
- name: `?Load@ImagePolicy@MitigationOptionsPolicy@@QEAA_NXZ`
- size: `539`
- prototype: `char __fastcall(MitigationOptionsPolicy::ImagePolicy *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009f70`
- `0x18000a5f0`
- `0x1800127a8`

## callees

- `0x18001086c`
- `0x180010d9c`
- `0x180012530`

## pseudocode

```c
char __fastcall MitigationOptionsPolicy::ImagePolicy::Load(MitigationOptionsPolicy::ImagePolicy *this)
{
  if ( MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 32))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 128))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 192))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 256))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 336))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 400))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 464))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 544))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 624))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 688))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 784))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 2976))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3040))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3104))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3168))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3264))
    && MitigationOptionsPolicy::Policy::Load((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3328)) )
  {
    return 1;
  }
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 32));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 128));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 192));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 256));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 336));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 400));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 464));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 544));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 624));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 688));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 784));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 2976));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3040));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3104));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3168));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3264));
  MitigationOptionsPolicy::Policy::Reset((MitigationOptionsPolicy::ImagePolicy *)((char *)this + 3328));
  return 0;
}

```

## disassembly

```asm
0x180012530  mov     [rsp+arg_0], rbx
0x180012535  push    rdi
0x180012536  sub     rsp, 20h
0x18001253a  mov     rbx, rcx
0x18001253d  add     rcx, 20h ; ' '; this
0x180012541  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x180012546  test    al, al
0x180012548  jz      loc_180012675
0x18001254e  lea     rcx, [rbx+80h]; this
0x180012555  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001255a  test    al, al
0x18001255c  jz      loc_180012675
0x180012562  lea     rcx, [rbx+0C0h]; this
0x180012569  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001256e  test    al, al
0x180012570  jz      loc_180012675
0x180012576  lea     rcx, [rbx+100h]; this
0x18001257d  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x180012582  test    al, al
0x180012584  jz      loc_180012675
0x18001258a  lea     rcx, [rbx+150h]; this
0x180012591  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x180012596  test    al, al
0x180012598  jz      loc_180012675
0x18001259e  lea     rcx, [rbx+190h]; this
0x1800125a5  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x1800125aa  test    al, al
0x1800125ac  jz      loc_180012675
0x1800125b2  lea     rcx, [rbx+1D0h]; this
0x1800125b9  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x1800125be  test    al, al
0x1800125c0  jz      loc_180012675
0x1800125c6  lea     rcx, [rbx+220h]; this
0x1800125cd  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x1800125d2  test    al, al
0x1800125d4  jz      loc_180012675
0x1800125da  lea     rcx, [rbx+270h]; this
0x1800125e1  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x1800125e6  test    al, al
0x1800125e8  jz      loc_180012675
0x1800125ee  lea     rcx, [rbx+2B0h]; this
0x1800125f5  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x1800125fa  test    al, al
0x1800125fc  jz      short loc_180012675
0x1800125fe  lea     rcx, [rbx+310h]; this
0x180012605  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001260a  test    al, al
0x18001260c  jz      short loc_180012675
0x18001260e  lea     rcx, [rbx+0BA0h]; this
0x180012615  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001261a  test    al, al
0x18001261c  jz      short loc_180012675
0x18001261e  lea     rcx, [rbx+0BE0h]; this
0x180012625  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001262a  test    al, al
0x18001262c  jz      short loc_180012675
0x18001262e  lea     rcx, [rbx+0C20h]; this
0x180012635  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001263a  test    al, al
0x18001263c  jz      short loc_180012675
0x18001263e  lea     rcx, [rbx+0C60h]; this
0x180012645  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001264a  test    al, al
0x18001264c  jz      short loc_180012675
0x18001264e  lea     rcx, [rbx+0CC0h]; this
0x180012655  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001265a  test    al, al
0x18001265c  jz      short loc_180012675
0x18001265e  lea     rcx, [rbx+0D00h]; this
0x180012665  call    ?Load@Policy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::Policy::Load(void)
0x18001266a  test    al, al
0x18001266c  jz      short loc_180012675
0x18001266e  mov     al, 1
0x180012670  jmp     loc_180012740
0x180012675  lea     rcx, [rbx+20h]; this
0x180012679  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x18001267e  lea     rcx, [rbx+80h]; this
0x180012685  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x18001268a  lea     rcx, [rbx+0C0h]; this
0x180012691  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x180012696  lea     rcx, [rbx+100h]; this
0x18001269d  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x1800126a2  lea     rcx, [rbx+150h]; this
0x1800126a9  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x1800126ae  lea     rcx, [rbx+190h]; this
0x1800126b5  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x1800126ba  lea     rcx, [rbx+1D0h]; this
0x1800126c1  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x1800126c6  lea     rcx, [rbx+220h]; this
0x1800126cd  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x1800126d2  lea     rcx, [rbx+270h]; this
0x1800126d9  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x1800126de  lea     rcx, [rbx+2B0h]; this
0x1800126e5  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x1800126ea  lea     rcx, [rbx+310h]; this
0x1800126f1  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x1800126f6  lea     rcx, [rbx+0BA0h]; this
0x1800126fd  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x180012702  lea     rcx, [rbx+0BE0h]; this
0x180012709  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x18001270e  lea     rcx, [rbx+0C20h]; this
0x180012715  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x18001271a  lea     rcx, [rbx+0C60h]; this
0x180012721  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x180012726  lea     rcx, [rbx+0CC0h]; this
0x18001272d  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x180012732  lea     rcx, [rbx+0D00h]; this
0x180012739  call    ?Reset@Policy@MitigationOptionsPolicy@@QEAAXXZ; MitigationOptionsPolicy::Policy::Reset(void)
0x18001273e  xor     al, al
0x180012740  mov     rbx, [rsp+28h+arg_0]
0x180012745  add     rsp, 20h
0x180012749  pop     rdi
0x18001274a  retn
```
